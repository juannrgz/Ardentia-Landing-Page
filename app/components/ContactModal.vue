<template>
  <Teleport to="body">
    <Transition
      enter-active-class="transition duration-300 ease-out"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="transition duration-200 ease-in"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <div 
        v-if="isOpen" 
        class="fixed inset-0 z-[100] flex items-center justify-center p-4 bg-black/60 backdrop-blur-sm"
        @click="close"
      >
        <div 
          class="relative w-full max-w-lg bg-[#0a0a0a] border border-white/10 rounded-2xl p-8 shadow-2xl overflow-hidden"
          @click.stop
        >
          <!-- Background Glows -->
          <div class="absolute top-0 right-0 w-[200px] h-[200px] bg-ardentia-purple/20 rounded-full blur-[80px] -translate-y-1/2 translate-x-1/2 pointer-events-none" />
          <div class="absolute bottom-0 left-0 w-[200px] h-[200px] bg-ardentia-pink/10 rounded-full blur-[80px] translate-y-1/2 -translate-x-1/2 pointer-events-none" />

          <button 
            @click="close"
            class="absolute top-4 right-4 text-zinc-400 hover:text-white transition-colors"
          >
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 18"/></svg>
          </button>

          <h3 class="text-2xl font-bold mb-2">Hablemos de tu proyecto</h3>
          <p class="text-zinc-400 mb-6 text-sm">Déjanos tus datos y te contactaremos en menos de 24h.</p>

          <form @submit.prevent="handleSubmit" class="space-y-4 relative z-10">
            <div>
              <label class="block text-xs font-medium text-zinc-500 mb-1 uppercase tracking-wider">Nombre Completo</label>
              <input 
                type="text" 
                v-model="form.name"
                class="w-full bg-white/5 border border-white/10 rounded-lg px-4 py-3 text-white placeholder-zinc-600 focus:outline-none focus:border-ardentia-purple focus:ring-1 focus:ring-ardentia-purple transition-all"
                placeholder="Ej. Juan Rodríguez"
                required
              />
            </div>
            
            <div>
              <label class="block text-xs font-medium text-zinc-500 mb-1 uppercase tracking-wider">Email</label>
              <input 
                type="email" 
                v-model="form.email"
                class="w-full bg-white/5 border border-white/10 rounded-lg px-4 py-3 text-white placeholder-zinc-600 focus:outline-none focus:border-ardentia-purple focus:ring-1 focus:ring-ardentia-purple transition-all"
                placeholder="tu@email.com"
                required
              />
            </div>

            <div>
              <label class="block text-xs font-medium text-zinc-500 mb-1 uppercase tracking-wider">Mensaje</label>
              <textarea 
                v-model="form.message"
                rows="4"
                class="w-full bg-white/5 border border-white/10 rounded-lg px-4 py-3 text-white placeholder-zinc-600 focus:outline-none focus:border-ardentia-purple focus:ring-1 focus:ring-ardentia-purple transition-all resize-none"
                placeholder="Cuéntanos sobre tu proyecto..."
                required
              ></textarea>
            </div>

            <button 
              type="submit"
              :disabled="isSubmitting"
              class="w-full py-3 bg-white text-black font-bold rounded-lg hover:bg-zinc-200 transition-all active:scale-[0.98] disabled:opacity-50 disabled:cursor-not-allowed"
            >
              {{ isSubmitting ? 'Enviando...' : 'Enviar Mensaje' }}
            </button>
          </form>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>

<script setup>
const { isOpen, close } = useContactModal()
const isSubmitting = ref(false)
const form = reactive({
  name: '',
  email: '',
  message: ''
})

const handleSubmit = async () => {
  isSubmitting.value = true
  
  // Reemplaza esta URL con la que obtendrás de Google Apps Script
  const SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbxCsRk3bmQXTO3NPJoHWhR3M_Mi2QcxGH-NcLLlMg9LDI9hjDDTX2q_KOwD2ceFyj5x9Q/exec'

  try {
    const formData = new FormData()
    formData.append('name', form.name)
    formData.append('email', form.email)
    formData.append('message', form.message)
    formData.append('timestamp', new Date().toISOString())

    await fetch(SCRIPT_URL, {
      method: 'POST',
      body: formData,
      mode: 'no-cors' // Google Script requiere no-cors o manejarlo específicamente
    })

    alert('¡Gracias! Hemos recibido tu mensaje y se ha guardado en Google Sheets.')
    close()
    form.name = ''
    form.email = ''
    form.message = ''
  } catch (error) {
    console.error('Error:', error)
    alert('Hubo un error al enviar el mensaje. Por favor, inténtalo de nuevo.')
  } finally {
    isSubmitting.value = false
  }
}
</script>

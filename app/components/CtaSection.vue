<template>
  <section id="contact" class="py-32 relative overflow-hidden">
    <!-- Seamless Top Transition -->
    <div class="absolute inset-x-0 top-0 h-32 bg-gradient-to-b from-ardentia-bg to-transparent z-0" />

    <!-- Glow Effect -->
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-full max-w-[1000px] h-[600px] bg-gradient-to-r from-ardentia-purple/10 via-ardentia-pink/5 to-ardentia-purple/10 rounded-full blur-[120px] pointer-events-none" />

    <div class="container mx-auto px-6 relative z-30 text-center">
      <h2 class="text-4xl md:text-6xl font-bold mb-8">
        Lleva tu negocio al <br />
        <span class="bg-clip-text text-transparent bg-gradient-to-r from-ardentia-purple to-ardentia-pink">siguiente nivel.</span>
      </h2>
      
      <p class="text-xl text-zinc-400 mb-12 max-w-2xl mx-auto">
        No solo creamos webs; construimos sistemas que trabajan para ti. Automatiza tu éxito y gana tiempo.
      </p>

      <div class="flex flex-col sm:flex-row gap-6 justify-center relative z-40">
        <button 
          @click="open"
          class="px-8 py-4 bg-white text-black font-bold rounded-full text-lg hover:bg-zinc-200 transition-all hover:scale-105 shadow-[0_0_30px_rgba(255,255,255,0.2)]"
        >
          Iniciar Proyecto
        </button>
        <a 
          href="https://www.instagram.com/ardentiasystems/"
          target="_blank"
          class="relative z-50 px-8 py-4 bg-black border border-zinc-800 text-white font-medium rounded-full text-lg hover:bg-zinc-900 transition-all flex items-center justify-center gap-2 pointer-events-auto"
        >
          <span>Síguenos en Instagram</span>
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-instagram"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
const { open } = useContactModal()
</script>

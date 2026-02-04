<template>
  <section class="min-h-screen relative flex flex-col items-center justify-center overflow-hidden pt-16 pb-12">
    <!-- Background Effects -->
    <div class="absolute inset-0 z-0">
      <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[600px] h-[600px] bg-ardentia-purple/20 rounded-full blur-[120px] opacity-70 animate-pulse" style="animation-duration: 8s" />
      <div class="absolute top-0 right-0 w-[400px] h-[400px] bg-ardentia-pink/10 rounded-full blur-[100px]" />
      <div class="absolute bottom-0 left-0 w-[400px] h-[400px] bg-ardentia-purple-glow/10 rounded-full blur-[100px]" />
    </div>

    <!-- Content -->
    <div class="relative z-10 container mx-auto px-6 text-center">
      <div 
        v-motion
        :initial="{ opacity: 0, y: 50, scale: 0.9 }"
        :enter="{ opacity: 1, y: 0, scale: 1, transition: { duration: 1000, type: 'spring', stiffness: 50 } }"
      >
        <h1 class="text-5xl md:text-7xl lg:text-8xl font-bold tracking-tighter mb-6 leading-tight">
          <span class="block text-white drop-shadow-lg">Tu web solo</span>
          <span class="block text-transparent bg-clip-text bg-gradient-to-r from-ardentia-purple via-ardentia-pink to-ardentia-purple bg-[length:200%_auto] animate-gradient">
            "está ahí"
          </span>
          <span class="block text-zinc-400 text-3xl md:text-5xl mt-2 font-medium tracking-tight">o realmente vende?</span>
        </h1>
        
        <p class="text-lg md:text-xl text-zinc-300 max-w-3xl mx-auto mb-8 leading-relaxed font-light">
          "Transformamos la chispa de tu negocio en una <span class="text-white font-medium">maquinaria digital de alto rendimiento</span>."
        </p>

        <div class="flex flex-col md:flex-row gap-4 justify-center items-center">
          <button 
            @click="open"
            class="px-8 py-4 bg-white text-black font-bold rounded-full text-lg hover:bg-zinc-200 transition-all hover:scale-105 active:scale-95 shadow-[0_0_20px_rgba(255,255,255,0.3)]"
          >
            Auditoría Gratuita
          </button>
          <a 
            href="https://github.com/juannrgz"
            target="_blank"
            class="px-8 py-4 bg-white/5 backdrop-blur-sm border border-white/10 text-white font-medium rounded-full text-lg hover:bg-white/10 transition-all flex items-center gap-2"
          >
            Ver Proyectos
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const { open } = useContactModal()
</script>

<style scoped>
.animate-gradient {
  animation: bg-pan 3s linear infinite;
}

@keyframes bg-pan {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
</style>

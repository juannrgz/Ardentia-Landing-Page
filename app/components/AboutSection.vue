<template>
  <section id="about" class="py-32 relative">
    <!-- Seamless transition gradient from top -->
    <div class="absolute inset-x-0 top-0 h-32 bg-gradient-to-b from-ardentia-bg to-transparent z-0" />
    
    <!-- Background Glow -->
    <div class="absolute top-1/2 right-0 -translate-y-1/2 w-[600px] h-[600px] bg-ardentia-purple/5 rounded-full blur-[120px] pointer-events-none" />

    <!-- Seamless Bottom Transition -->
    <div class="absolute inset-x-0 bottom-0 h-32 bg-gradient-to-t from-ardentia-bg to-transparent z-0" />

    <div class="container mx-auto px-6 flex flex-col md:flex-row items-center gap-16 relative z-10">
      <!-- Text Content -->
      <div class="flex-1 order-2 md:order-1">
        <h2 class="text-3xl md:text-5xl font-bold mb-8">Más que una agencia, <span class="bg-clip-text text-transparent bg-gradient-to-r from-white to-zinc-500">somos arquitectos.</span></h2>
        
        <div class="prose prose-invert prose-lg text-zinc-400">
          <p class="mb-6">
            <strong class="text-white">Ardentia Systems</strong> es un estudio boutique especializado en la arquitectura digital y la optimización de negocios. Nacemos de la necesidad de cerrar la brecha entre una estética impecable y una funcionalidad técnica avanzada.
          </p>
          <p>
            El nombre <span class="text-ardentia-pink">"Ardentia"</span> sugiere energía y movimiento, mientras que <span class="text-ardentia-purple">"Systems"</span> da la seguridad de que hay orden y metodología detrás.
          </p>
          <p class="mt-6 border-l-4 border-ardentia-purple pl-4 italic text-zinc-300">
            "Nuestra metodología transforma simples conceptos en ecosistemas digitales estratégicos. Al construir sistemas escalables y no solo páginas aisladas, garantizamos que tu presencia digital sea tu activo más valioso."
          </p>
        </div>
      </div>

      <!-- Visual Element -->
      <div 
        class="flex-1 order-1 md:order-2 flex justify-center relative"
        v-motion
        :initial="{ opacity: 0, x: 50 }"
        :enter="{ opacity: 1, x: 0, transition: { duration: 800 } }"
      >
        <div class="relative w-full max-w-[500px] aspect-square">
          <div class="absolute inset-0 bg-gradient-to-tr from-ardentia-purple to-ardentia-pink rounded-full blur-[80px] opacity-20 animate-pulse" />
          <div class="relative z-10 w-full h-full bg-gradient-to-br from-zinc-900/80 to-black/40 backdrop-blur-xl border border-white/10 rounded-3xl p-8 flex flex-col items-center justify-center text-center overflow-hidden group hover:border-ardentia-purple/30 transition-all duration-500">
             
             <!-- Abstract Graphic -->
             <div class="relative w-40 h-40 mb-8 flex items-center justify-center">
                <!-- Orbits -->
                <div class="absolute inset-0 border border-white/10 rounded-full animate-[spin_8s_linear_infinite]" />
                <div class="absolute inset-4 border border-ardentia-purple/30 rounded-full animate-[spin_12s_linear_infinite_reverse]" />
                
                <!-- Core Glow -->
                <div class="absolute inset-8 bg-gradient-to-tr from-ardentia-purple via-ardentia-pink to-transparent rounded-full blur-2xl opacity-30 animate-pulse" />
                
                <!-- Center Icon -->
                <div class="relative z-10 bg-white/5 p-4 rounded-2xl border border-white/10 backdrop-blur-sm">
                   <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2v20"/><path d="m2 12 20 0"/><path d="m4.93 4.93 14.14 14.14"/><path d="m19.07 4.93-14.14 14.14"/></svg>
                </div>
             </div>

             <h3 class="text-2xl font-bold mb-3 text-white">Excelencia Digital</h3>
             
             <p class="text-zinc-400 text-sm mb-8 leading-relaxed">
               "Donde la estrategia de negocio se encuentra con la perfección técnica."
             </p>

             <!-- Metrics -->
             <div class="grid grid-cols-2 gap-4 w-full">
                <div class="bg-white/5 rounded-2xl p-4 border border-white/5 hover:bg-white/10 transition-colors">
                    <div class="text-ardentia-purple font-bold text-xl mb-1">100%</div>
                    <div class="text-[10px] uppercase tracking-widest text-zinc-500">A Medida</div>
                </div>
                <div class="bg-white/5 rounded-2xl p-4 border border-white/5 hover:bg-white/10 transition-colors">
                    <div class="text-ardentia-pink font-bold text-xl mb-1">Premium</div>
                    <div class="text-[10px] uppercase tracking-widest text-zinc-500">Calidad</div>
                </div>
             </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

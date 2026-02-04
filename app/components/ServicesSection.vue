<template>
  <section id="services" class="py-32 relative">
    <div class="container mx-auto px-6">
      <div class="mb-20">
        <h2 class="text-3xl md:text-5xl font-bold mb-6"> <span class="text-ardentia-purple">Arquitectura</span> Digital</h2>
        <p class="text-zinc-400 max-w-xl text-lg">
          Nacemos de la necesidad de cerrar la brecha entre una estética impecable y una funcionalidad técnica avanzada.
        </p>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <!-- Card 1 -->
        <div 
          class="group p-8 rounded-3xl bg-white/5 border border-white/10 hover:border-ardentia-purple/50 transition-all hover:bg-white/10 hover:-translate-y-2 duration-300 relative overflow-hidden"
          v-motion-slide-visible-once-bottom
        >
          <div class="absolute inset-0 bg-gradient-to-br from-ardentia-purple/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500" />
          
          <div class="relative z-10">
            <div class="w-12 h-12 rounded-2xl bg-black/50 border border-white/10 flex items-center justify-center mb-6 text-2xl">
              💻
            </div>
            <h3 class="text-2xl font-bold mb-4">Desarrollo Ecosistémico</h3>
            <p class="text-zinc-400 leading-relaxed">
              Creación de landing pages y plataformas ultra rápidas utilizando las últimas tecnologías. No solo webs, sino sistemas vivos.
            </p>
          </div>
        </div>

        <!-- Card 2 -->
        <div 
          class="group p-8 rounded-3xl bg-white/5 border border-white/10 hover:border-ardentia-pink/50 transition-all hover:bg-white/10 hover:-translate-y-2 duration-300 relative overflow-hidden"
          v-motion-slide-visible-once-bottom
          :delay="100"
        >
          <div class="absolute inset-0 bg-gradient-to-br from-ardentia-pink/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500" />
          
          <div class="relative z-10">
            <div class="w-12 h-12 rounded-2xl bg-black/50 border border-white/10 flex items-center justify-center mb-6 text-2xl">
              🤖
            </div>
            <h3 class="text-2xl font-bold mb-4">Eficiencia Operativa</h3>
            <p class="text-zinc-400 leading-relaxed">
              Implementación de flujos de trabajo automatizados para que las empresas recuperen su recurso más valioso: el tiempo.
            </p>
          </div>
        </div>

        <!-- Card 3 -->
        <div 
          class="group p-8 rounded-3xl bg-white/5 border border-white/10 hover:border-purple-500/50 transition-all hover:bg-white/10 hover:-translate-y-2 duration-300 relative overflow-hidden"
          v-motion-slide-visible-once-bottom
          :delay="200"
        >
          <div class="absolute inset-0 bg-gradient-to-br from-purple-500/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500" />
          
          <div class="relative z-10">
            <div class="w-12 h-12 rounded-2xl bg-black/50 border border-white/10 flex items-center justify-center mb-6 text-2xl">
              📈
            </div>
            <h3 class="text-2xl font-bold mb-4">Expansión de Marca</h3>
            <p class="text-zinc-400 leading-relaxed">
              Estrategias de presencia digital diseñadas para posicionar a empresas y profesionales como referentes en su sector.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

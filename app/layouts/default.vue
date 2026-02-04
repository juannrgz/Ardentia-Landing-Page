<template>
  <div class="min-h-screen flex flex-col font-sans bg-ardentia-bg text-white selection:bg-ardentia-purple selection:text-white">
    <!-- Header -->
    <header class="fixed top-0 left-0 right-0 z-50 backdrop-blur-md border-b border-white/5 bg-ardentia-bg/80">
      <div class="container mx-auto px-6 h-16 flex items-center">
        <!-- Logo (Left) -->
        <div class="flex-1 flex justify-start">
          <NuxtLink to="/" class="flex items-center gap-3 hover:opacity-80 transition-opacity cursor-pointer">
            <img src="/logo.png" alt="Ardentia Icon" class="h-8 w-auto" />
            <span class="font-bold text-xl tracking-tight hidden sm:inline-block">Ardentia<span class="text-zinc-400 font-normal">Systems</span></span>
          </NuxtLink>
        </div>
        
        <!-- Nav (Center) -->
        <nav class="hidden md:flex gap-8 text-sm font-medium text-zinc-400">
          <a href="#services" class="hover:text-white transition-colors">Servicios</a>
          <a href="#about" class="hover:text-white transition-colors">Nosotros</a>
          <a href="#contact" class="hover:text-white transition-colors">Contacto</a>
        </nav>

        <!-- Button (Right) -->
        <div class="flex-1 flex justify-end">
          <button 
            @click="open"
            class="px-4 py-2 text-sm font-medium bg-white text-black rounded-full hover:bg-zinc-200 transition-colors"
          >
            Hablemos
          </button>
        </div>
      </div>
    </header>

    <!-- Main Content -->
    <main class="flex-grow pt-16">
      <slot />
    </main>

    <!-- Footer -->
    <footer class="py-12 border-t border-white/5 bg-black/50">
      <div class="container mx-auto px-6 text-center">
        <p class="text-zinc-500 text-sm">
          &copy; {{ new Date().getFullYear() }} Ardentia Systems. Arquitectura Digital.
        </p>
      </div>
    </footer>

    <ContactModal />
  </div>
</template>

<script setup>
const { open } = useContactModal()
</script>

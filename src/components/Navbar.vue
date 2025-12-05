<template>
  <header
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
    :class="
      scrolled ? 'bg-[#0a0a0a]/95 backdrop-blur-md shadow-lg shadow-black/20' : 'bg-transparent'
    "
  >
    <div class="container mx-auto px-6 py-4">
      <div class="flex items-center justify-between">
        <!-- Logo with Profile Image -->
        <a href="#me" class="flex items-center gap-3">
          <img
            src="@/assets/image/james_espana.jpeg"
            alt="James España"
            class="w-8 h-8 sm:w-10 sm:h-10 rounded-full border-2 border-amber-500 object-cover"
          />
          <span class="text-lg sm:text-xl font-bold text-gradient hidden sm:block"
            >James España</span
          >
        </a>

        <!-- Desktop Navigation -->
        <nav class="hidden md:flex items-center gap-8">
          <a
            v-for="link in navLinks"
            :key="link.href"
            :href="link.href"
            class="text-gray-300 hover:text-amber-500 transition-colors relative group font-medium"
          >
            {{ link.name }}
            <span
              class="absolute -bottom-1 left-0 w-0 h-0.5 bg-amber-500 transition-all duration-300 group-hover:w-full"
            ></span>
          </a>
        </nav>

        <!-- Mobile Menu Toggle -->
        <button @click="mobileOpen = !mobileOpen" class="md:hidden text-white p-2">
          <svg
            v-if="!mobileOpen"
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            ></path>
          </svg>
          <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            ></path>
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <transition name="slide">
        <nav v-if="mobileOpen" class="md:hidden mt-4 pb-4 border-t border-gray-800 pt-4">
          <a
            v-for="link in navLinks"
            :key="link.href"
            :href="link.href"
            @click="mobileOpen = false"
            class="block py-3 text-gray-300 hover:text-amber-500 transition-colors font-medium"
          >
            {{ link.name }}
          </a>
        </nav>
      </transition>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const scrolled = ref(false)
const mobileOpen = ref(false)

const navLinks = [
  { name: 'Home', href: '#me' },
  { name: 'About', href: '#about' },
  { name: 'Resume', href: '#resume' },
  { name: 'Portfolio', href: '#portfolio' },
  { name: 'Contact', href: '#contact' },
]

const handleScroll = () => {
  scrolled.value = window.scrollY > 50
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s ease;
}
.slide-enter-from,
.slide-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>

<template>
  <div class="min-h-screen">
    <!-- Animated Background -->
    <div class="fixed inset-0 -z-10 overflow-hidden">
      <div class="absolute inset-0 bg-[#0a0a0a]"></div>
      <div
        class="absolute top-0 -left-40 w-80 h-80 bg-amber-500/20 rounded-full mix-blend-multiply filter blur-3xl animate-pulse-slow"
      ></div>
      <div
        class="absolute top-1/2 -right-40 w-80 h-80 bg-yellow-500/20 rounded-full mix-blend-multiply filter blur-3xl animate-pulse-slow"
        style="animation-delay: 2s"
      ></div>
      <div
        class="absolute -bottom-40 left-1/2 w-80 h-80 bg-orange-600/20 rounded-full mix-blend-multiply filter blur-3xl animate-pulse-slow"
        style="animation-delay: 4s"
      ></div>
    </div>

    <Navbar />
    <main>
      <Hero />
      <About />
      <Resume />
      <Portfolio />
      <Contact />
    </main>
    <Footer />
    <ScrollTop />
  </div>
</template>

<script setup>
import { onMounted } from 'vue'
import AOS from 'aos'
import 'aos/dist/aos.css'

import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Resume from './components/Resume.vue'
import Portfolio from './components/Portfolio.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'
import ScrollTop from './components/ScrollTop.vue'

onMounted(() => {
  AOS.init({
    duration: 800,
    easing: 'ease-out-cubic',
    once: true,
    offset: 50,
  })
})
</script>

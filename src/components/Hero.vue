<template>
  <section id="me" class="min-h-screen flex items-center relative overflow-hidden">
    <!-- Background Image -->
    <div class="absolute inset-0 z-0">
      <img
        src="@/assets/image/me.jpg"
        alt="Background"
        class="w-full h-full object-cover object-center"
      />
      <!-- Dark Overlay -->
      <div class="absolute inset-0 bg-black/60"></div>
    </div>

    <div class="container mx-auto px-6 sm:px-8 lg:px-16 relative z-20">
      <div class="max-w-3xl" data-aos="fade-up">
        <!-- Name & Title -->
        <h2
          class="text-2xl sm:text-3xl md:text-4xl text-white mb-2"
          data-aos="fade-up"
          data-aos-delay="200"
        >
          I am,
        </h2>
        <h1
          class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl font-bold mb-6"
          data-aos="fade-up"
          data-aos-delay="300"
        >
          <span class="text-gradient italic">James España</span>
        </h1>

        <!-- Typing Effect with Cursor -->
        <div
          class="text-base sm:text-lg md:text-xl lg:text-2xl text-white mb-8 font-mono"
          data-aos="fade-up"
          data-aos-delay="400"
        >
          <span class="text-white font-semibold">Console.WriteLine("</span>
          <span class="text-amber-500">a </span>
          <span class="text-gradient font-semibold">{{ displayedText }}</span>
          <span class="cursor" :class="{ 'cursor-blink': !isTyping }">|</span>
          <span class="text-white font-semibold">");</span>
        </div>

        <!-- Social Links -->
        <div class="flex gap-4" data-aos="fade-up" data-aos-delay="500">
          <a
            href="https://web.facebook.com/jamesgomezjusto.espana/"
            target="_blank"
            class="w-10 h-10 sm:w-12 sm:h-12 border-2 border-amber-500 text-amber-500 hover:bg-amber-500 hover:text-black rounded-full flex items-center justify-center transition-all duration-300 hover:scale-110"
          >
            <svg class="w-4 h-4 sm:w-5 sm:h-5" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
              />
            </svg>
          </a>
          <a
            href="https://github.com/jmsespana"
            target="_blank"
            class="w-10 h-10 sm:w-12 sm:h-12 border-2 border-amber-500 text-amber-500 hover:bg-amber-500 hover:text-black rounded-full flex items-center justify-center transition-all duration-300 hover:scale-110"
          >
            <svg class="w-4 h-4 sm:w-5 sm:h-5" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
              />
            </svg>
          </a>
          <a
            href="mailto:jamesespana308@gmail.com"
            class="w-10 h-10 sm:w-12 sm:h-12 border-2 border-amber-500 text-amber-500 hover:bg-amber-500 hover:text-black rounded-full flex items-center justify-center transition-all duration-300 hover:scale-110"
          >
            <svg class="w-4 h-4 sm:w-5 sm:h-5" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"
              />
            </svg>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const roles = ['Student', 'Designer', 'Jr. Developer', 'Full Stack Developer']
const displayedText = ref('')
const isTyping = ref(true)
let roleIndex = 0
let charIndex = 0
let isDeleting = false
let timeout: ReturnType<typeof setTimeout>

const typeEffect = () => {
  const currentRole = roles[roleIndex]
  if (!currentRole) return

  if (!isDeleting) {
    // Typing
    displayedText.value = currentRole.substring(0, charIndex + 1)
    charIndex++
    isTyping.value = true

    if (charIndex === currentRole.length) {
      // Pause before deleting
      isTyping.value = false
      timeout = setTimeout(() => {
        isDeleting = true
        typeEffect()
      }, 2000)
      return
    }
  } else {
    // Deleting
    displayedText.value = currentRole.substring(0, charIndex - 1)
    charIndex--
    isTyping.value = true

    if (charIndex === 0) {
      isDeleting = false
      roleIndex = (roleIndex + 1) % roles.length
    }
  }

  const speed = isDeleting ? 50 : 100
  timeout = setTimeout(typeEffect, speed)
}

onMounted(() => {
  typeEffect()
})

onUnmounted(() => clearTimeout(timeout))
</script>

<style scoped>
.cursor {
  display: inline-block;
  margin-left: 2px;
  font-weight: bold;
  color: #f59e0b;
}

.cursor-blink {
  animation: blink 1s step-end infinite;
}

@keyframes blink {
  0%,
  50% {
    opacity: 1;
  }
  51%,
  100% {
    opacity: 0;
  }
}
</style>

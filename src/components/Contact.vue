<template>
  <section id="contact" class="py-16 sm:py-20 lg:py-24 px-4 sm:px-6 bg-gray-900/50">
    <div class="container mx-auto">
      <!-- Section Title -->
      <div class="text-center mb-10 sm:mb-16" data-aos="fade-up">
        <h2 class="section-title">Contact <span class="text-gradient">Me</span></h2>
        <p class="text-gray-400 mt-4 text-sm sm:text-base">
          If you're interested in my work, you can find my contact details below!
        </p>
        <div
          class="w-20 h-1 bg-gradient-to-r from-amber-500 to-yellow-500 rounded mx-auto mt-4"
        ></div>
      </div>

      <!-- Contact Cards -->
      <div
        class="grid sm:grid-cols-2 md:grid-cols-3 gap-4 sm:gap-6 lg:gap-8 max-w-4xl mx-auto mb-10 sm:mb-16"
      >
        <!-- Address -->
        <div class="card text-center group" data-aos="fade-up" data-aos-delay="100">
          <div
            class="w-16 h-16 bg-amber-500/20 rounded-full flex items-center justify-center mx-auto mb-4 group-hover:bg-amber-500/30 transition-colors"
          >
            <svg
              class="w-7 h-7 text-amber-500"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"
              ></path>
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"
              ></path>
            </svg>
          </div>
          <h3 class="text-xl font-bold text-gradient mb-2">Address</h3>
          <p class="text-gray-400">Brgy. Bonbon Butuan City,<br />Agusan Del Norte</p>
        </div>

        <!-- Phone -->
        <div class="card text-center group" data-aos="fade-up" data-aos-delay="200">
          <div
            class="w-16 h-16 bg-amber-500/20 rounded-full flex items-center justify-center mx-auto mb-4 group-hover:bg-amber-500/30 transition-colors"
          >
            <svg
              class="w-7 h-7 text-amber-500"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"
              ></path>
            </svg>
          </div>
          <h3 class="text-xl font-bold text-gradient mb-2">Call Me</h3>
          <a href="tel:+639925650401" class="text-gray-400 hover:text-amber-500 transition-colors">
            +63 992 565 0401
          </a>
        </div>

        <!-- Email -->
        <div class="card text-center group" data-aos="fade-up" data-aos-delay="300">
          <div
            class="w-16 h-16 bg-amber-500/20 rounded-full flex items-center justify-center mx-auto mb-4 group-hover:bg-amber-500/30 transition-colors"
          >
            <svg
              class="w-7 h-7 text-amber-500"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
              ></path>
            </svg>
          </div>
          <h3 class="text-xl font-bold text-gradient mb-2">Email Me</h3>
          <a
            href="mailto:jamesespana308@gmail.com"
            class="text-gray-400 hover:text-amber-500 transition-colors"
          >
            jamesespana308@gmail.com
          </a>
        </div>
      </div>

      <!-- Contact Form -->
      <div class="max-w-2xl mx-auto" data-aos="fade-up" data-aos-delay="400">
        <form @submit.prevent="handleSubmit" class="card">
          <div class="grid md:grid-cols-2 gap-6 mb-6">
            <div>
              <label class="block text-gray-300 mb-2 font-medium">Your Name</label>
              <input
                v-model="form.name"
                type="text"
                required
                class="w-full px-4 py-3 bg-[#0a0a0a] border border-gray-700 rounded-xl focus:outline-none focus:border-amber-500 transition-colors"
                placeholder="James España"
              />
            </div>
            <div>
              <label class="block text-gray-300 mb-2 font-medium">Your Email</label>
              <input
                v-model="form.email"
                type="email"
                required
                class="w-full px-4 py-3 bg-[#0a0a0a] border border-gray-700 rounded-xl focus:outline-none focus:border-amber-500 transition-colors"
                placeholder="your@email.com"
              />
            </div>
          </div>
          <div class="mb-6">
            <label class="block text-gray-300 mb-2 font-medium">Subject</label>
            <input
              v-model="form.subject"
              type="text"
              required
              class="w-full px-4 py-3 bg-[#0a0a0a] border border-gray-700 rounded-xl focus:outline-none focus:border-amber-500 transition-colors"
              placeholder="Project Inquiry"
            />
          </div>
          <div class="mb-6">
            <label class="block text-gray-300 mb-2 font-medium">Message</label>
            <textarea
              v-model="form.message"
              rows="5"
              required
              class="w-full px-4 py-3 bg-[#0a0a0a] border border-gray-700 rounded-xl focus:outline-none focus:border-amber-500 transition-colors resize-none"
              placeholder="Your message here..."
            ></textarea>
          </div>
          <button type="submit" class="btn-primary w-full flex items-center justify-center gap-2">
            Send Message
            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M14 5l7 7m0 0l-7 7m7-7H3"
              ></path>
            </svg>
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive } from 'vue'

const form = reactive({
  name: '',
  email: '',
  subject: '',
  message: '',
})

const handleSubmit = () => {
  const mailtoLink = `mailto:jamesespana308@gmail.com?subject=${encodeURIComponent(form.subject)}&body=${encodeURIComponent(`Name: ${form.name}\nEmail: ${form.email}\n\n${form.message}`)}`
  window.location.href = mailtoLink
}
</script>

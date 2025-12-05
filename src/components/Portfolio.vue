<template>
  <section id="portfolio" class="py-16 sm:py-20 lg:py-24 px-4 sm:px-6">
    <div class="container mx-auto">
      <!-- Section Title -->
      <div class="text-center mb-8 sm:mb-12" data-aos="fade-up">
        <h2 class="section-title">My <span class="text-gradient">Projects / Certificates</span></h2>
        <p class="text-gray-400 mt-4 text-sm sm:text-base">
          Feel free to explore my works and credentials below!
        </p>
        <div
          class="w-20 h-1 bg-gradient-to-r from-amber-500 to-yellow-500 rounded mx-auto mt-4"
        ></div>
      </div>

      <!-- Filter Buttons -->
      <div
        class="flex flex-wrap justify-center gap-2 sm:gap-4 mb-8 sm:mb-12"
        data-aos="fade-up"
        data-aos-delay="100"
      >
        <button
          v-for="filter in filters"
          :key="filter.value"
          @click="activeFilter = filter.value"
          class="px-4 sm:px-6 py-2 text-sm sm:text-base rounded-full font-medium transition-all duration-300"
          :class="
            activeFilter === filter.value
              ? 'bg-gradient-to-r from-amber-500 to-yellow-500 text-gray-900'
              : 'bg-gray-900 border border-gray-700 text-gray-300 hover:border-amber-500 hover:text-amber-500'
          "
        >
          {{ filter.name }}
        </button>
      </div>

      <!-- Portfolio Grid -->
      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6 lg:gap-8">
        <transition-group name="portfolio">
          <div
            v-for="(item, index) in filteredItems"
            :key="item.title"
            class="card group overflow-hidden"
            data-aos="zoom-in"
            :data-aos-delay="index * 100"
          >
            <!-- Image -->
            <div class="relative -mx-6 -mt-6 mb-4 sm:mb-6 h-40 sm:h-48 overflow-hidden">
              <div
                class="w-full h-full bg-gradient-to-br flex items-center justify-center text-5xl sm:text-6xl"
                :class="
                  item.type === 'project'
                    ? 'from-amber-500/30 to-orange-600/30'
                    : 'from-blue-600/30 to-purple-600/30'
                "
              >
                {{ item.emoji }}
              </div>
              <!-- Overlay -->
              <div
                class="absolute inset-0 bg-[#0a0a0a]/80 opacity-0 group-hover:opacity-100 transition-all duration-300 flex items-center justify-center gap-4"
              >
                <button
                  @click="openModal(item)"
                  class="w-12 h-12 bg-amber-500 rounded-full flex items-center justify-center text-gray-900 transform scale-0 group-hover:scale-100 transition-transform duration-300 hover:bg-yellow-500"
                >
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0zM10 7v3m0 0v3m0-3h3m-3 0H7"
                    ></path>
                  </svg>
                </button>
              </div>
            </div>

            <!-- Content -->
            <span
              class="text-xs font-semibold px-3 py-1 rounded-full"
              :class="
                item.type === 'project'
                  ? 'bg-amber-500/20 text-amber-500'
                  : 'bg-blue-500/20 text-blue-400'
              "
            >
              {{ item.type === 'project' ? 'Project' : 'Certificate' }}
            </span>
            <h3 class="text-xl font-bold mt-3 mb-2 group-hover:text-gradient transition-colors">
              {{ item.title }}
            </h3>
            <p class="text-gray-400 text-sm">{{ item.description }}</p>
          </div>
        </transition-group>
      </div>
    </div>

    <!-- Modal -->
    <transition name="fade">
      <div
        v-if="modalOpen"
        class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-[#0a0a0a]/90 backdrop-blur-sm"
        @click.self="modalOpen = false"
      >
        <div class="card max-w-2xl w-full max-h-[90vh] overflow-y-auto" data-aos="zoom-in">
          <div class="flex justify-between items-start mb-4">
            <h3 class="text-2xl font-bold text-gradient">{{ selectedItem?.title }}</h3>
            <button @click="modalOpen = false" class="text-gray-400 hover:text-white">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M6 18L18 6M6 6l12 12"
                ></path>
              </svg>
            </button>
          </div>
          <div
            class="h-64 bg-gradient-to-br from-amber-500/20 to-yellow-500/20 rounded-xl flex items-center justify-center text-8xl mb-6"
          >
            {{ selectedItem?.emoji }}
          </div>
          <p class="text-gray-300">
            {{ selectedItem?.fullDescription || selectedItem?.description }}
          </p>
        </div>
      </div>
    </transition>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

interface PortfolioItem {
  title: string
  description: string
  fullDescription?: string
  emoji: string
  type: 'project' | 'certificate'
}

const activeFilter = ref('all')
const modalOpen = ref(false)
const selectedItem = ref<PortfolioItem | null>(null)

const filters = [
  { name: 'All', value: 'all' },
  { name: 'Projects', value: 'project' },
  { name: 'Certificates', value: 'certificate' },
]

const items: PortfolioItem[] = [
  {
    title: 'CampusCare Application',
    description: 'Connecting, Communicating, Improving: CampusCare',
    fullDescription:
      '"Connecting, Communicating, Improving: CampusCare" - This application is designed to facilitate seamless communication between university students, staff, and administration.',
    emoji: '📱',
    type: 'project',
  },
  {
    title: 'CampusCare Dashboard',
    description: 'Admin dashboard for CampusCare management',
    fullDescription:
      'Administrative dashboard for the CampusCare application, providing analytics and management tools for university administration.',
    emoji: '💻',
    type: 'project',
  },
  {
    title: 'CampusCare Mobile',
    description: 'Mobile version of CampusCare app',
    fullDescription:
      'Cross-platform mobile application for CampusCare, enabling students to access services on the go.',
    emoji: '🚀',
    type: 'project',
  },
  {
    title: 'HTML Certificate',
    description: 'Introduction to HTML - January 22, 2024',
    emoji: '🏆',
    type: 'certificate',
  },
  {
    title: 'CSS Certificate',
    description: 'Introduction to CSS - January 26, 2024',
    emoji: '🎨',
    type: 'certificate',
  },
  {
    title: 'JavaScript Certificate',
    description: 'Introduction to JavaScript - March 12, 2024',
    emoji: '⚡',
    type: 'certificate',
  },
  {
    title: 'Java Certificate',
    description: 'Introduction to Java - April 15, 2024',
    emoji: '☕',
    type: 'certificate',
  },
  {
    title: 'Java Intermediate',
    description: 'Java Intermediate Course - April 20, 2024',
    emoji: '🔥',
    type: 'certificate',
  },
]

const filteredItems = computed(() => {
  if (activeFilter.value === 'all') return items
  return items.filter((item) => item.type === activeFilter.value)
})

const openModal = (item: PortfolioItem) => {
  selectedItem.value = item
  modalOpen.value = true
}
</script>

<style scoped>
.portfolio-enter-active,
.portfolio-leave-active {
  transition: all 0.5s ease;
}
.portfolio-enter-from,
.portfolio-leave-to {
  opacity: 0;
  transform: scale(0.8);
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>

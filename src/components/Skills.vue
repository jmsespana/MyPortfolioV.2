<template>
  <section id="skills" class="py-20 bg-slate-900 text-white">
    <div class="container mx-auto px-6">
      <h2 class="text-4xl font-bold text-center mb-12" data-aos="fade-up">
        🚀 Tools I Use
      </h2>
      <div class="grid grid-cols-3 md:grid-cols-6 gap-8 max-w-4xl mx-auto">
        <div v-for="skill in skills" :key="skill.name" 
             class="flex flex-col items-center p-4 bg-slate-800 rounded-xl hover:bg-slate-700 transition-all transform hover:scale-110"
             data-aos="zoom-in">
          <img :src="skill.icon" :alt="skill.name" class="w-12 h-12 mb-2" />
          <span class="text-sm text-gray-300">{{ skill.name }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skills = [
  { name: 'Vue.js', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg' },
  { name: 'JavaScript', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original. svg' },
  { name: 'Python', icon: 'https://cdn. jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg' },
  { name: 'Java', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original-wordmark. svg' },
  { name: 'PostgreSQL', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg' },
  { name: 'Flutter', icon: 'https://cdn.jsdelivr. net/gh/devicons/devicon/icons/flutter/flutter-original.svg' },
  { name: 'Dart', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dart/dart-original. svg' },
  { name: 'HTML5', icon: 'https://cdn. jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original-wordmark.svg' },
  { name: 'CSS3', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original-wordmark.svg' },
  { name: 'Bootstrap', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-plain.svg' },
  { name: 'Vuetify', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuetify/vuetify-original.svg' },
  { name: 'C', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original. svg' },
]
</script>
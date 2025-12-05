<template>
  <section id="about" class="py-16 sm:py-20 lg:py-24 px-4 sm:px-6">
    <div class="container mx-auto">
      <!-- Section Title -->
      <div class="text-center mb-10 sm:mb-16" data-aos="fade-up">
        <h2 class="section-title">About <span class="text-gradient">Me</span></h2>
        <div
          class="w-20 h-1 bg-gradient-to-r from-amber-500 to-yellow-500 rounded mx-auto mt-4"
        ></div>
      </div>

      <div class="grid lg:grid-cols-2 gap-8 lg:gap-12 items-center max-w-6xl mx-auto">
        <!-- Image Side -->
        <div class="flex justify-center" data-aos="fade-right">
          <div class="relative">
            <div
              class="absolute -inset-4 bg-gradient-to-r from-amber-500 to-yellow-500 rounded-2xl blur opacity-25"
            ></div>
            <img
              src="@/assets/image/james_espana.jpeg"
              alt="James España"
              class="relative w-64 h-64 sm:w-72 sm:h-72 md:w-80 md:h-80 object-cover rounded-2xl border-4 border-amber-500"
            />
          </div>
        </div>

        <!-- Content Side -->
        <div data-aos="fade-left" class="text-center lg:text-left">
          <h3 class="text-xl sm:text-2xl font-bold mb-4">
            Full Stack Developer & <span class="text-gradient">Tech Enthusiast</span>
          </h3>
          <p class="text-gray-400 leading-relaxed mb-4 sm:mb-6 text-sm sm:text-base">
            I'm a passionate full stack developer and BS Information Technology student at
            <span class="text-amber-500 font-medium">Caraga State University</span>. I love creating
            beautiful, functional, and user-friendly web applications.
          </p>
          <p class="text-gray-400 leading-relaxed mb-4 sm:mb-6 text-sm sm:text-base">
            With experience in both frontend and backend technologies, I enjoy bringing ideas to
            life through clean, efficient code. I'm always eager to learn new technologies and take
            on challenging projects.
          </p>

          <!-- Info List -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 sm:gap-4 mb-6 sm:mb-8">
            <div class="flex items-center gap-3 justify-center lg:justify-start">
              <span class="w-2 h-2 bg-amber-500 rounded-full"></span>
              <span class="text-gray-300 text-sm sm:text-base"
                ><strong>Name:</strong> James España</span
              >
            </div>
            <div class="flex items-center gap-3 justify-center lg:justify-start">
              <span class="w-2 h-2 bg-amber-500 rounded-full"></span>
              <span class="text-gray-300 text-sm sm:text-base"
                ><strong>From:</strong> Philippines 🇵🇭</span
              >
            </div>
            <div class="flex items-center gap-3 justify-center lg:justify-start">
              <span class="w-2 h-2 bg-amber-500 rounded-full"></span>
              <span class="text-gray-300 text-sm sm:text-base"
                ><strong>Role:</strong> Full Stack Developer</span
              >
            </div>
            <div class="flex items-center gap-3 justify-center lg:justify-start">
              <span class="w-2 h-2 bg-amber-500 rounded-full"></span>
              <span class="text-gray-300 text-sm sm:text-base"
                ><strong>Email:</strong> jamesespana308</span
              >
            </div>
          </div>

          <a href="#contact" class="btn-primary"> Let's Talk </a>
        </div>
      </div>
    </div>
  </section>
</template>

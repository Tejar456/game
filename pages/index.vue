<template>
  <div class="h-screen relative">
    <img src="assets/img/bg.webp" alt="Background" class="w-full h-full object-cover absolute inset-0">

    <div class="relative h-full flex items-center justify-center p-4 md:p-5">
      <div class="border-2 border-green-900 p-4 md:p-8 rounded-xl bg-gradient-to-br bg-white
        backdrop-blur-sm shadow-xl w-full max-w-[800px] mx-4">
        <div class="flex justify-end mb-2 md:mb-4">
          <nuxt-link to="/info">

            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
              stroke="currentColor" class="size-8 md:size-10 text-green-600 animate-bounce hover:text-green-800">
              <path stroke-linecap="round" stroke-linejoin="round"
                d="m11.25 11.25.041-.02a.75.75 0 0 1 1.063.852l-.708 2.836a.75.75 0 0 0 1.063.853l.041-.021M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Zm-9-3.75h.008v.008H12V8.25Z" />
            </svg>
          </nuxt-link>
        </div>

        <div class="space-y-4 md:space-y-6">
          <h1 class="text-center text-2xl md:text-4xl font-sans font-bold text-green-950 mb-10 md:mb-20">
            Komponen Ekosistem Lingkungan
          </h1>


          <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
            <NuxtLink to="/play">
              <button class="w-48 md:w-64 px-4 md:px-6 py-3 md:py-4 bg-green-600 text-white text-lg md:text-xl 
        font-semibold font-sans rounded-full hover:bg-green-700 transform hover:scale-105 transition-all duration-300 
        shadow-lg hover:shadow-xl">
                Mainkan Quiz
              </button>
            </NuxtLink>

            <NuxtLink to="/materi">
              <button class="w-48 md:w-64 px-4 md:px-6 py-3 md:py-4 bg-green-600 text-white text-lg md:text-xl 
        font-semibold font-sans rounded-full hover:bg-green-700 transform hover:scale-105 transition-all duration-300 
        shadow-lg hover:shadow-xl">
                Baca Materi
              </button>
            </NuxtLink>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeIn {
  animation: fadeIn 1s ease-out;
}
</style>
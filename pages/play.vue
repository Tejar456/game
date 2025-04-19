<template>
  <div class="h-screen relative overflow-y-auto">
    <img src="assets/img/5.webp" alt="Background" class="w-full h-full object-cover fixed inset-0">

    <div class="relative min-h-screen flex items-center justify-center py-6 px-4">
      <NuxtLink to="/" class="absolute top-4 left-4 p-2 bg-white hover:bg-white rounded-full 
        transition-all duration-300 backdrop-blur-sm group">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor"
          class="w-8 h-8 text-green-800 group-hover:scale-110 transition-transform duration-300">
          <path stroke-linecap="round" stroke-linejoin="round" d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18" />
        </svg>
      </NuxtLink>
      <div
        class="absolute top-4 right-4 bg-white text-green-800 font-bold text-lg px-4 py-2 rounded-full shadow-lg backdrop-blur-sm z-50">
        {{ formattedTime }}
      </div>

      <div
        class="border-2 border-green-800 p-4 sm:p-6 md:p-8 rounded-xl bg-white backdrop-blur-sm shadow-xl w-full max-w-[800px] mx-auto">
        <h1 class="text-2xl md:text-3xl font-sans font-bold text-green-800 text-center mb-8">
          Quiz Komponen Ekosistem Lingkungan
        </h1>

        <div v-if="!quizFinished" class="space-y-6">
          <div v-if="currentQuestion"
            class="bg-transparent border border-green-500 p-6 rounded-xl h-[320px] md:h-[200px] flex justify-between flex-col">
            <h2 class="text-xl md:text-2xl font-semibold text-green-950 mb-6">
              {{ currentIndex + 1 }}. {{ currentQuestion.question }}
            </h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <button v-for="(option, index) in shuffledOptions" :key="index" @click="checkAnswer(option)" class="w-full px-6 py-4 bg-green-600 text-white text-lg md:text-xl 
                font-semibold font-sans rounded-full hover:bg-green-700 transform hover:scale-105 transition-all duration-300 
                shadow-lg hover:shadow-xl">
                {{ option }}
              </button>
            </div>
          </div>
        </div>

        <div v-else
          class="text-center space-y-6 bg-transparent border border-green-500 p-6 rounded-xl h-[320px] md:h-[200px]">
          <div class="relative">
            <div v-if="isPerfectScore" class="absolute left-1/2 -translate-x-1/2 -top-20">
              <ConfettiExplosion :particleCount="100" :force="0.3" :duration="3000" />
            </div>

            <h2 class="text-2xl md:text-3xl font-bold text-green-950 ">
              {{ isPerfectScore ? 'Selamat! Nilai Sempurna! 🎉' : 'Quiz Selesai!' }}
            </h2>
            <p class="text-xl text-green-900">Skor Anda: {{ score }} / {{ selectedQuestions.length }}</p>

            <div class="flex flex-col sm:flex-row gap-3 sm:gap-4 justify-center mt-14 md:mt-6 sm:mt-8">
              <button @click="startQuiz" class="w-full sm:w-auto px-4 sm:px-6 py-2.5 sm:py-3 
        bg-green-600 text-white text-base sm:text-lg
        font-semibold rounded-full hover:bg-green-700 
        transform hover:scale-105 transition-all duration-300 
        shadow-lg hover:shadow-xl">
                Main Lagi
              </button>

              <NuxtLink to="/" class="w-full sm:w-auto">
                <button class="w-full px-4 sm:px-6 py-2.5 sm:py-3
          bg-transparent border-2 border-green-600 text-green-600 
          text-base sm:text-lg font-semibold rounded-full 
          hover:bg-green-50 transform hover:scale-105 
          transition-all duration-300 shadow-lg hover:shadow-xl">
                  Kembali
                </button>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.transform {
  transition: transform 0.3s ease;
}

.hover\:scale-102:hover {
  transform: scale(1.02);
}

.timer {
  transition: all 0.3s ease;
}
</style>

<script>
import ConfettiExplosion from 'vue-confetti-explosion'

export default {
  components: {
    ConfettiExplosion
  },
  data() {
    return {
      questions: [
        {
          question: "Tanah termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik",
        },
        {
          question: "Air termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik",
        },
        {
          question: "Batu termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik",
        },

        {
          question: "Rumput termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik",
        },
        {
          question: "Pasir termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik",
        },
        {
          question: "Pohon mangga yang menghasilkan buah merupakan komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Air yang dibutuhkan tumbuhan untuk pertumbuhan termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik"
        },
        {
          question: "Ulat yang memakan daun di kebun termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Bakteri yang menguraikan sisa-sisa organisme termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Cahaya matahari yang digunakan untuk fotosintesis adalah komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik"
        },
        {
          question: "Jamur pengurai yang menguraikan daun jatuh merupakan komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Tanah sebagai media tumbuh tanaman termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik"
        },
        {
          question: "Kupu-kupu yang membantu penyerbukan bunga adalah komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Suhu udara yang mempengaruhi pertumbuhan tanaman termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik"
        },
        {
          question: "Burung pemakan serangga dalam ekosistem termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Kelembaban udara yang mempengaruhi kehidupan tumbuhan termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik"
        },
        {
          question: "Ikan termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik",
        },

        {
          question: "Gunung termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik",
        },
        {
          question: "Hewan herbivora yang memakan tumbuhan termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Udara yang diperlukan untuk pernapasan termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik"
        },
        {
          question: "Tumbuhan hijau yang melakukan fotosintesis termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Cacing tanah yang menggemburkan tanah termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "Mineral dalam tanah yang dibutuhkan tumbuhan termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik"
        },
        {
          question: "Semut yang membuat sarang di tanah termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Biotik"
        },
        {
          question: "pH tanah yang mempengaruhi pertumbuhan tanaman termasuk komponen?",
          options: ["Biotik", "Abiotik"],
          answer: "Abiotik"
        }
      ],
      selectedQuestions: [],
      currentIndex: 0,
      score: 0,
      quizFinished: false,
      timer: 60,
      intervalId: null,
    };
  },
  computed: {
    currentQuestion() {
      return this.selectedQuestions[this.currentIndex];
    },
    shuffledOptions() {
      return this.currentQuestion
        ? this.shuffleArray([...this.currentQuestion.options])
        : [];
    },
    isPerfectScore() {
      return this.quizFinished && this.score === this.selectedQuestions.length;
    },
    formattedTime() {
      const minutes = Math.floor(this.timer / 60);
      const seconds = this.timer % 60;
      return `${minutes}:${seconds.toString().padStart(2, '0')}`;
    },
  },
  methods: {
    startQuiz() {
      this.selectedQuestions = this.shuffleArray([...this.questions]).slice(0, 5);
      this.currentIndex = 0;
      this.score = 0;
      this.quizFinished = false;
      this.startTimer();
    },
    shuffleArray(array) {
      return array.sort(() => Math.random() - 0.5);
    },
    checkAnswer(option) {
      if (option === this.currentQuestion.answer) {
        this.score++;
      }
      if (this.currentIndex < this.selectedQuestions.length - 1) {
        this.currentIndex++;
      } else {
        this.quizFinished = true;
        clearInterval(this.intervalId);
      }
    },
    startTimer() {
      if (this.intervalId) clearInterval(this.intervalId);
      this.timer = 60;
      this.intervalId = setInterval(() => {
        if (this.timer > 0) {
          this.timer--;
        } else {
          clearInterval(this.intervalId);
          this.quizFinished = true;
        }
      }, 1000);
    },
  },
  created() {
    this.startQuiz();
  },
  beforeDestroy() {
    if (this.intervalId) clearInterval(this.intervalId);
  },
};
</script>

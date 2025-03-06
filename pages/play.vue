<template>
    <div class="p-6 max-w-xl mx-auto">
      <h1 class="text-2xl font-bold text-center">Kel</h1>
      <div v-if="!quizFinished">
        <div v-if="currentQuestion" class="mt-4">
          <h2 class="text-lg font-semibold">
            {{ currentIndex + 1 }}. {{ currentQuestion.question }}
          </h2>
          <div class="mt-2">
            <button
              v-for="(option, index) in shuffledOptions"
              :key="index"
              @click="checkAnswer(option)"
              class="block w-full px-4 py-2 mt-2 bg-blue-500 text-white rounded-md hover:bg-blue-700"
            >
              {{ option }}
            </button>
          </div>
        </div>
      </div>
      <div v-else class="mt-4 text-center">
        <h2 class="text-xl font-bold">Quiz Selesai!</h2>
        <p>Skor Anda: {{ score }} / {{ selectedQuestions.length }}</p>
        <button
          @click="startQuiz"
          class="mt-4 px-4 py-2 bg-green-500 text-white rounded-md"
        >
          Main Lagi
        </button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
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
            question: "Udara termasuk komponen?",
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
            question: "Ikan termasuk komponen?",
            options: ["Biotik", "Abiotik"],
            answer: "Biotik",
          },
          {
            question: "Matahari termasuk komponen?",
            options: ["Biotik", "Abiotik"],
            answer: "Abiotik",
          },
          {
            question: "Gunung termasuk komponen?",
            options: ["Biotik", "Abiotik"],
            answer: "Abiotik",
          },
          {
            question: "Jamur termasuk komponen?",
            options: ["Biotik", "Abiotik"],
            answer: "Biotik",
          },
        ],
        selectedQuestions: [],
        currentIndex: 0,
        score: 0,
        quizFinished: false,
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
    },
    methods: {
      startQuiz() {
        this.selectedQuestions = this.shuffleArray([...this.questions]).slice(
          0,
          5
        );
        this.currentIndex = 0;
        this.score = 0;
        this.quizFinished = false;
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
        }
      },
    },
    created() {
      this.startQuiz();
    },
  };
  </script>
  
  <style>
  body {
    font-family: Arial, sans-serif;
  }
  </style>
  
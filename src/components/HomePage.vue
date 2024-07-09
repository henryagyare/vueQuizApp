<template>
  <main class="flex h-screen items-center justify-center bg-gray-100">
    <!-- quiz container -->
    <div
      class="bg-white overflow-hidden relative flex-none container shadow-lg rounded-lg px-12 py-6"
    >
      <!-- image tag -->
      <img src="../assets/images/abstract.svg" class="object-none absolute -top-10 left-0" alt="" />

      <!-- contents -->
      <div class="relative z-20">
        <!-- score container -->
        <div class="text-right text-gray-800">
          <p class="text-small leading-3">Score</p>
          <p class="font-bold">60</p>
        </div>

        <!-- Timer container -->
        <div class="bg-white mt-4 shadow-lg p-1 rounded-full w-full h-5">
          <div class="bg-blue-700 rounded-full w-11/12 h-full"></div>
        </div>

        <!-- question container -->
        <div class="rounded-lg mt-8 bg-gray-100 p-2 neumorph-1 text-center font-bold text-gray-800">
          <div class="bg-white p-5">What is the most popular city in Italy?</div>
        </div>
        <!-- options container -->
        <div class="mt-8">
          <!-- option container -->
          <div class="neumorph-1 option-wrong bg-gray-100 p-2 rounded-lg relative">
            <div
              class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
            >
              <p class="transform -rotate-45">+10</p>
            </div>
            <div class="rounded-lg font-bold flex p-2">
              <!-- option id -->
              <div class="p-3 rounded-lg">A</div>
              <!-- option name -->
              <div class="flex items-center pl-6">Milan</div>
            </div>
          </div>

          <div class="neumorph-1 option-default bg-gray-100 p-2 rounded-lg relative">
            <div
              class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
            >
              <p class="transform -rotate-45">+10</p>
            </div>
            <div class="rounded-lg font-bold flex p-2">
              <!-- option id -->
              <div class="p-3 rounded-lg">B</div>
              <!-- option name -->
              <div class="flex items-center pl-6">Florence</div>
            </div>
          </div>

          <div class="neumorph-1 option-correct bg-gray-100 p-2 rounded-lg relative">
            <div
              class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
            >
              <p class="transform -rotate-45">+10</p>
            </div>
            <div class="rounded-lg font-bold flex p-2">
              <!-- option id -->
              <div class="p-3 rounded-lg">C</div>
              <!-- option name -->
              <div class="flex items-center pl-6">Rome</div>
            </div>
          </div>

          <div class="neumorph-1 option-default bg-gray-100 p-2 rounded-lg relative">
            <div
              class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
            >
              <p class="transform -rotate-45">+10</p>
            </div>
            <div class="rounded-lg font-bold flex p-2">
              <!-- option id -->
              <div class="p-3 rounded-lg">D</div>
              <!-- option name -->
              <div class="flex items-center pl-6">Naples</div>
            </div>
          </div>
        </div>
        <!-- progress indicator container -->
        <div class="mt-8 text-center">
          <div class="h-1 w-12 bg-gray-800 rounded-full mx-auto"></div>
          <p class="font-bold text-gray-800">2/50</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style>
.neumorph-1 {
  box-shadow:
    6px 6px rgba(0, 0, 0, 0.09),
    -6px -6px 18px #ffffff;
}

.container {
  max-width: 600px;
  border-radius: 25px;
}
</style>

<script>
import { ref } from 'vue'; // we use "ref" if we want to create a variable whose value will be changed in the template
export default {
  setup() {
    // data

    let question_counter = ref(0)


    const currentQuestion = ref({
      question: '',
      answer: 1,
      choices: []
    })

    const dummyQuestions = [
      {
        question: 'What is the most popular city in America?',
        answer: 1,
        choices: ['New York', 'Los Angeles', 'Chicago', 'Houston']
      },
      {
        question: 'What is the most popular city in Spain?',
        answer: 2,
        choices: ['Madrid', 'Barcelona', 'Valencia', 'Sevilla']
      },
      {
        question: 'What is the most popular city in France?',
        answer: 1,
        choices: ['Paris', 'Marseille', 'Lyon', 'Toulouse']
      }
    ]
    
    const onQuizStart = () => {
      currentQuestion.value = dummyQuestions[question_counter.value] // doing currentQuestion.value helps us to be able to access the value of the currentQuestion ref
      question_counter.value = 0

      // currentQuestion.value = dummyQuestions[question_counter.value]
      // question_counter.value = 0
    }


    return { currentQuestion, dummyQuestions, question_counter }
  }
}
</script>

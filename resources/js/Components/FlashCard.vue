<!-- resources/js/Components/FlashCard.vue -->
<template>
    <div @click="flipped = !flipped" class="cursor-pointer perspective">
      <div
        class="relative w-full h-72 transition-transform duration-700 transform-style-preserve-3d"
        :class="{ 'rotate-y-180': flipped }"
      >
        <!-- Cara frontal -->
        <div
          class="absolute w-full h-full bg-white rounded-lg shadow-lg flex flex-col items-center justify-center backface-hidden p-4"
        >
          <img :src="image" alt="" class="h-16 mb-2" />
          <p class="text-indigo-600 font-bold text-lg">{{ title }}</p>
        </div>

        <!-- Cara trasera -->
        <div
          class="absolute w-full h-full bg-indigo-600 text-white rounded-lg shadow-lg backface-hidden transform rotate-y-180 p-4 flex items-center justify-center text-sm text-justify"
        >
          <p>{{ description }}</p>
        </div>
      </div>
    </div>
  </template>

  <script setup>
  import { ref } from 'vue'
  defineProps(['title', 'description', 'image'])
  const flipped = ref(false)
  </script>

  <style scoped>
  .perspective {
    perspective: 1000px;
  }
  .rotate-y-180 {
    transform: rotateY(180deg);
  }
  .backface-hidden {
    backface-visibility: hidden;
  }
  .transform-style-preserve-3d {
    transform-style: preserve-3d;
  }
  </style>

<template>
  <div
    v-if="isOpen"
    class="fixed inset-0 bg-opacity-50 flex items-center justify-center z-50"
  >
    <div class="bg-white p-6 rounded-lg shadow-lg w-96 relative">
      <button
        @click="$emit('close')"
        class="absolute top-2 right-2 text-gray-600 hover:text-gray-800"
      >
        &times;
      </button>

      <h2 class="text-xl font-bold mb-4 text-center">{{ title }}</h2>
      <p class="text-gray-700 text-center">{{ text }}</p>
      <a :href="site" target="_blank" class="flex flex-col items-center space-y-3 bg-white p-4 rounded-lg shadow hover:bg-gray-200 transition"> Visite o site</a>
     
    
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  site: String,
  text: String,
  isOpen: Boolean,
});
</script>

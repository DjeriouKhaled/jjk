<template>
    <!-- v-if will only render the toast if 'visible' is true -->
    <div v-if="visible" class="fixed bottom-4 left-1/2 transform -translate-x-1/2 bg-gray-800 text-white p-4 rounded-md shadow-lg z-50">
      {{ message }}
    </div>
  </template>
  
  <script>
  export default {
    props: {
      message: {
        type: String,
        required: true,
      },
      visible: {
        type: Boolean,
        default: false, // Default to false, meaning it's hidden by default
      },
    },
  }
  </script>
  
  <style scoped>
  /* Optional custom styles */
  </style>
  
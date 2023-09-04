<template>
  <div  id="contact" class="mainConDiv">
    <h1 class="text-center">Contact</h1>
    <form @submit.prevent="sendEmail">
      <div class="mb-4">
        <label for="name" class="block text-sm font-medium text-gray-700">Name</label>
        <input type="text" id="name" v-model="name" class="w-full px-3 py-2 border border-gray-300 rounded-md" required />
      </div>
      <div class="mb-4">
        <label for="subject" class="block text-sm font-medium text-gray-700">Subject</label>
        <input type="text" id="subject" v-model="subject" class="w-full px-3 py-2 border border-gray-300 rounded-md" required />
      </div>
      <div class="mb-4">
        <label for="message" class="block text-sm font-medium text-gray-700">Message</label>
        <textarea id="message" v-model="message" class="w-full px-3 py-2 border border-gray-300 rounded-md" rows="4" required></textarea>
      </div>
      <div>
        <button type="submit" class="px-4 py-2 text-white bg-blue-500 rounded-md hover:bg-blue-600">Send</button>
      </div>
    </form>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const name = ref('');
const subject = ref('');
const message = ref('');

function sendEmail() {
}
</script>

<style scoped>
.mainConDiv {
  border: 2px solid brown;
  height: 900px;
}

</style>

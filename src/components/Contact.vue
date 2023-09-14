<template>
  <div id="contact" class="mainConDiv p-6 md:p-12">
    <h1 class="text-center text-3xl font-semibold mb-6 conHead">Contact Us</h1>
    <form @submit.prevent="sendEmail" class="w-full md:max-w-lg mx-auto">
      <div class="mb-4">
        <label for="name" class="block text-sm font-medium">Name</label>
        <input
          type="text"
          id="name"
          v-model="name"
          class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring focus:border-blue-500"
          required
        />
      </div>
      <div class="mb-4">
        <label for="subject" class="block text-sm font-medium">Subject</label>
        <input
          type="text"
          id="subject"
          v-model="subject"
          class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring focus:border-blue-500"
          required
        />
      </div>
      <div class="mb-6">
        <label for="message" class="block text-sm font-medium">Message</label>
        <textarea
          id="message"
          v-model="message"
          class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring focus:border-blue-500"
          rows="4"
          required
        ></textarea>
      </div>
      <div class="text-center">
        <button
          type="submit"
          class="px-6 py-3 text-white bg-blue-500 rounded-md hover:bg-blue-600 focus:outline-none focus:ring focus:border-blue-500"
        >
          Send
        </button>
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
  // Implement your email sending logic here
}
</script>

<style scoped>
.mainConDiv {
  border: 2px solid brown;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.conHead {
  margin-top: -30vh;
}


</style>

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
          class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring "
          required
        />
      </div>
      <div class="mb-4">
        <label for="subject" class="block text-sm font-medium">Subject</label>
        <input
          type="text"
          id="subject"
          v-model="subject"
          class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring"
          required
        />
      </div>
      <div class="mb-6">
        <label for="message" class="block text-sm font-medium">Message</label>
        <textarea
          id="message"
          v-model="message"
          class="w-full px-4 py-2 border rounded-md focus:outline-none focus:ring"
          rows="4"
          required
        ></textarea>
      </div>
      <div class="text-center">
        <button
          type="submit"
          class="px-6 py-3 rounded-md focus:outline-none focus:ring contactBut"
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
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.conHead {
  margin-top: -30vh;
}

.contactBut {
  background-color: linear-gradient(315deg, rgb(29, 255, 25) 3%, rgba(48, 238, 226, 1) 38%, rgba(60, 132, 206, 1) 68%, rgba(101, 0, 94, 1) 98%); 
  border-radius: 10px;
  border: 3px solid white;
}


</style>

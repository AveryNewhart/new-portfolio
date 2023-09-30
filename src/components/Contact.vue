<template>
  <div id="contact" class="mainConDiv p-6 md:p-12">
    <h1 class="text-center text-3xl font-semibold mb-6 conHead">Contact Me</h1>
    <form @submit.prevent="sendEmail" class="w-full md:max-w-lg mx-auto">
      <div class="mb-4">
        <label for="name" class="block text-sm font-medium theLabels">Name</label>
        <input
          type="text"
          id="name"
          v-model="name"
          class="w-full px-4 py-2 border rounded-md "
          required
        />
      </div>
      <div class="mb-4">
        <label for="subject" class="block text-sm font-medium theLabels">E-Mail</label>
        <input
          type="text"
          id="subject"
          v-model="subject"
          class="w-full px-4 py-2 border rounded-md"
          required
        />
      </div>
      <div class="mb-6">
        <label for="message" class="block text-sm font-medium theLabels">Message</label>
        <textarea
          id="message"
          v-model="message"
          class="w-full px-4 py-2 border rounded-md"
          rows="4"
          required
        ></textarea>
      </div>
      <div class="text-center">
        <button
          type="submit"
          class="px-6 py-3 rounded-md contactBut"
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

h1 {
  padding: 20px;
  font-size: 45px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect, with no background color, it just makes the h1 pop more since same background color as pages background */
}

.mainConDiv {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.theLabels {
  font-family: 'Gaegu';
}

.conHead {
  margin-top: -30vh;
  font-family: 'Gaegu';
}

.contactBut {
  background-color: linear-gradient(315deg, rgb(29, 255, 25) 3%, rgba(48, 238, 226, 1) 38%, rgba(60, 132, 206, 1) 68%, rgba(101, 0, 94, 1) 98%); 
  border-radius: 10px;
  border: 3px solid white;
  font-family: 'Gaegu';
  font-size: 1.5rem;
}

.contactBut:hover {
  background-image: linear-gradient(30deg,#f5b6b3,#6272fc);
  transform: scale(0.9);
  transition-duration: 1s ease-out;
  /* box-shadow: #030557 0px 25px 35px -13px; */
  color:#ffffeb;
  border:0.1px  #6e0175;
  -webkit-tap-highlight-color: transparent;
  animation-play-state: paused;
}

input:focus,
textarea:focus {
  border: 5px solid white;
}


</style>

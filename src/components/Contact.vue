<template>
  <div id="contact" class="mainConDiv p-6 md:p-12">
    <h1 class="text-center text-3xl font-semibold mb-6 conHead">Contact Me</h1>
    <form ref="form" @submit.prevent="sendEmail" class="w-full md:max-w-lg mx-auto">
      <div class="mb-4">
        <label class="text-sm font-medium theLabels">Name</label>
        <input
          type="text"
          name="user_name"
          class="w-full px-4 py-2 border rounded-md userInputs"
          required
        />
      </div>
      <div class="mb-4">
        <label class="text-sm font-medium theLabels">E-Mail</label>
        <input
          type="text"
          name="user_email"
          class="w-full px-4 py-2 border rounded-md userInputs"
          required
        />
      </div>
      <div class="mb-6">
        <label class="text-sm font-medium theLabels">Message</label>
        <textarea
          name="message"
          class="w-full px-4 py-2 border rounded-md userInputs"
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
import { ref } from "vue";
import * as emailjs from "@emailjs/browser";

const form = ref<HTMLFormElement | null>(null);

const sendEmail = (e: Event) => {
  e.preventDefault();

  if (form.value) {
    emailjs
      .sendForm(
        "service_bou8hac",
        "template_3o83xpc",
        form.value,
        "jqm10N66yC4KZBrhY"
      )
      .then(
        (result) => {
          console.log(result.text);
          // Reset the form fields
          if (form.value) {
            form.value.reset();
          }
        },
        (error) => {
          console.error(error.text);
        }
      );
  }
};

</script>

<style scoped>

h1 {
  padding: 20px;
  font-size: 45px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect, with no background color, it just makes the h1 pop more since same background color as pages background */
}

.userInputs {
  font-family: 'Gauegu';
  background-color: #925ff0;
  border: 1px solid #a3fda1;
  color: white;
  margin-top: 5px;
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
  /* background-color: rgba(255, 255, 255, 0.3); Brighter background with the same translucency */
  background-color: #a3fda1;
  border: 1px solid #925ff0;
  color: #2d2d2d;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect */
  padding: 5px;
  border-radius: 10px;
}

.conHead {
  margin-top: -30vh;
  font-family: 'Gaegu';
  /* text-decoration: dashed underline white; */
  color: #a3fda1;
  border: 3px solid #925ff0;
}

.contactBut {
  /* background-color: rgba(255, 255, 255, 0.3); Brighter background with the same translucency */
  background-color: #a3fda1;
  border: 3px solid #925ff0;
  color: #2d2d2d;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect */
  border-radius: 10px;
  /* border: 3px solid white; */
  font-family: 'Gaegu';
  font-size: 1.5rem;
}

.contactBut:hover {
  /* background-image: linear-gradient(30deg,#f5b6b3,#6272fc); */
  background-color: #925ff0;
  border: 3px solid #a3fda1;
  transform: scale(0.9);
  transition-duration: 1s ease-out;
  /* box-shadow: #030557 0px 25px 35px -13px; */
  color:#ffffeb;
  /* border:0.1px  #6e0175;
  -webkit-tap-highlight-color: transparent;
  animation-play-state: paused; */
}

input:focus,
textarea:focus {
  border: 5px solid white;
}


</style>

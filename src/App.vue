<script setup lang="ts">
// @ts-ignore
import Background from './components/Background.vue';
import Nav from './components/Nav.vue';
import About from './components/About.vue';
import Projects from './components/Projects.vue';
import Resume from './components/Resume.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
import Backend from './components/Backend.vue';
import FullStack from './components/Fullstack.vue';

import { ref } from 'vue';

const currentSection = ref<number>(0);

const navigate = (direction: number) => {
  const newSection = currentSection.value + direction;
  if (newSection >= 0 && newSection <= 5) {
    currentSection.value = newSection;
    window.scrollTo(0, newSection * window.innerHeight);
  }
};


</script>

<template>
  <div id="app">
    <Background />
    <div class="componentDiv">
      <Nav />
      <div class="section aboutDiv" v-show="currentSection === 0">
        <About />
      </div>
      <div class="section projectDiv" v-show="currentSection === 1">
        <Projects />
      </div>
      <div class="section projectDiv" v-show="currentSection === 2">
        <Backend />
      </div>
      <div class="section projectDiv" v-show="currentSection === 3">
        <FullStack />
      </div>
      <div class="section resumeDiv" v-show="currentSection === 4">  
        <Resume />
      </div>
      <div class="section contactDiv" v-show="currentSection === 5">  
        <Contact />
      </div>
      <div>
        <Footer />
      </div>
      <div class="arrow left" @click="navigate(-1)" v-show="currentSection > 0"></div>
      <div class="arrow right" @click="navigate(1)" v-show="currentSection < 5"></div>
    </div>
  </div>
</template>


<style scoped>

.projectDiv {
  margin-top: 10px;
  margin-bottom: 10px;
}

.section {
  min-height: 100vh;
}

.arrow {
    position: fixed;
    top: 50%;
    transform: translateY(-50%);
    width: 30px;
    height: 30px;
    background-color: #333;
    opacity: 0.7;
    cursor: pointer;
  }

  .left {
    left: 20px;
  }

  .right {
    right: 20px;
  }

</style>

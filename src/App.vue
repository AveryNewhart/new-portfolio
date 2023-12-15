<script setup lang="ts">
/* add fontawesome core */
import { library } from '@fortawesome/fontawesome-svg-core'

/* add some free styles */
import { faTwitter } from '@fortawesome/free-brands-svg-icons'
import { faArrowLeft } from '@fortawesome/free-solid-svg-icons'
import { faArrowRight } from '@fortawesome/free-solid-svg-icons'



/* add each imported icon to the library */
library.add(faTwitter, faArrowLeft, faArrowRight)

// @ts-ignore
// import Background from './components/Background.vue';
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

  const navigateTo = (sectionId: string) => {
  let newSection = currentSection.value;

  if (sectionId === 'prev') {
    newSection = Math.max(0, currentSection.value - 1);
  } else if (sectionId === 'next') {
    newSection = Math.min(5, currentSection.value + 1);
  } else {
    // Handle section IDs like 'about1', 'projects1', etc.
    switch (sectionId) {
      case 'about1':
        newSection = 0;
        break;
      case 'projects1':
        newSection = 1;
        break;
      case 'backend1':
        newSection = 2;
        break;
      case 'fullstack1':
        newSection = 3;
        break;
      case 'resume1':
        newSection = 4;
        break;
      case 'contact1':
        newSection = 5;
        break;
    }
  }

  currentSection.value = newSection;
  window.scrollTo(0, newSection * window.innerHeight);
};

</script>

<template>
  <div id="app">
    <!-- <Background /> -->
    <div class="componentDiv">
      <Nav @navigate="navigateTo" />
      <div class="section aboutDiv" v-if="currentSection === 0">
        <About id="about1"/>
      </div>
      <div class="section projectDiv" v-if="currentSection === 1">
        <Projects id="projects1"/>
      </div>
      <div class="section projectDiv" v-if="currentSection === 2">
        <Backend id="backend1"/>
      </div>
      <div class="section projectDiv" v-if="currentSection === 3">
        <FullStack id="fullstack1"/>
      </div>
      <div class="section resumeDiv" v-if="currentSection === 4">  
        <Resume id="resume1"/>
      </div>
      <div class="section contactDiv" v-if="currentSection === 5">  
        <Contact id="contact1"/>
      </div>
      <div>
        <Footer />
      </div>
      <!-- <font-awesome-icon icon="fa-brands fa-twitter" /> -->
      <!-- <font-awesome-icon :icon="['fas', 'arrow-left']" /> -->
      <div class="arrow left" @click="navigateTo('prev')" v-show="currentSection > 0"><font-awesome-icon :icon="['fas', 'arrow-left']" beat-fade /></div>
      <div class="arrow right" @click="navigateTo('next')" v-show="currentSection < 5"><font-awesome-icon :icon="['fas', 'arrow-right']" beat-fade /></div>
    </div>
  </div>
</template>



<style scoped>

/* .projectDiv {
  margin-top: 10px;
  margin-bottom: 10px;
} */

#app {
  background-color: #2d2d2d;
}

.section {
  min-height: 100vh;
}

.arrow {
    position: fixed;
    top: 96.5%;
    transform: translateY(-50%);
    /* width: 30px;
    height: 30px; */
    /* background-color: #333; */
    opacity: 0.7;
    cursor: pointer;
    font-size: 35px;
  }

  .left {
    left: 20px;
  }

  .right {
    right: 20px;
  }

</style>

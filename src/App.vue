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


</script>

<template>
  <div id="app">
    <Background />
    <div class="componentDiv">
      <Nav />
      <h2 class="bold text-white">make it so page snaps to whichever section the user is looking at.</h2>
      <div class="section aboutDiv">
        <About />
      </div>
      <div class="section projectDiv">
        <Projects />
        <Backend />
        <FullStack />
      </div>
      <div class="section resumeDiv">  
        <Resume />
      </div>
      <div class="section contactDiv">  
        <Contact />
      </div>
      <div class="">
        <Footer />
      </div>
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

</style>

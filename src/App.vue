<script setup lang="ts">
// @ts-ignore
import Background from './components/Background.vue';
import Nav from './components/Nav.vue';
import About from './components/About.vue';
import Projects from './components/Projects.vue';
import Resume from './components/Resume.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';


</script>

<template>
  <div id="app">
    <Background />
    <div class="componentDiv">
      <Nav />
      <div class="aboutDiv">
        <About />
      </div>
      <div class="projectDiv">
        <Projects />
      </div>
      <div class="resumeDiv">  
        <Resume />
      </div>
      <div class="contactDiv">  
        <Contact />
      </div>
      <Footer />
    </div>
  </div>
</template>

<style scoped>

.projectDiv {
  margin-top: 10px;
  margin-bottom: 10px;
}

</style>

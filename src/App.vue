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
      <About />
      <Projects />
      <Resume />
      <Contact />
      <Footer />
    </div>
  </div>
</template>

<style scoped>

h1 {
  text-align: center;
  font-size: 25px;
  font-weight: bold;
}


</style>

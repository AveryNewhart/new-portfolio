<script setup lang="ts">
// @ts-ignore
import Background from './components/Background.vue';


</script>

<template>
  <div id="app">
    <Background />
    <div class="componentDiv">
      <h1>component nav</h1>
      <h1>component about</h1>
      <h1>component porjects</h1>
      <h1>component resume</h1>
      <h1>component contact</h1>
      <h1>component footer</h1>
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

<script setup lang="ts">

import { ref } from 'vue';

const currentPosition = ref(0);

const updatePosition = (index: number) => {
  currentPosition.value = index;
};


interface Backend {
    title: string;
    image: string;
    video: string;
    language: string;
    about: string;
    repo: string;
}

const backends: Backend[] = [
    {
        title: 'README Generator',
        image: '/images/readMeGen.png',
        video: 'https://github.com/AveryNewhart/README-Generator',
        language: 'JavaScript',
        about: 'i love creating read meeeeeeeeesssss about section',
        repo: 'https://github.com/AveryNewhart/README-Generator',
    },
    {
        title: 'Social Network Backend',
        image: '/images/socialNetworkBackend.png',
        video: 'https://drive.google.com/file/d/1Niv2UUrKq0y4PreW8bW5NCwMH163WCtw/view',
        language: 'JavaScript',
        about: 'i love social netowrking about section',
        repo: 'https://github.com/AveryNewhart/Social-Network-Backend',
    },
    {
        title: 'E-Commerce Site',
        image: '/images/eCommerce.png',
        video: 'ecommercevideo.webm',
        language: 'languages used here, js',
        about: 'i love ecommerceeee about section',
        repo: 'https://github.com/AveryNewhart/E-Commerce-Site',
    },
    {
        title: 'Employee Tracker',
        image: '/images/employeeTracker.png',
        video: 'employee-tracker-vid.webm',
        language: 'JavaScript',
        about: 'i love tracking employeeeeees about section',
        repo: 'https://github.com/AveryNewhart/Employee-Tracker',
    },
    {
        title: 'Team Profile Generator',
        image: '/images/teamProfGen.png',
        video: 'teamgen.webm',
        language: 'JavaScript',
        about: 'i love creating team profiles about section',
        repo: 'https://github.com/AveryNewhart/Team-Profile-Generator',
    },
];



</script>

<template>
  <div class="mainProjDiv">

  <div class="mainProjectDivs">
      <h3>Backend</h3>
     <div class="bigBody">
      <input type="radio" name="position" v-for="(backend, index) in backends" :key="backend.title" :id="'position-' + index" @click="updatePosition(index)" />
      <main id="carousel1">
        <div class="item" v-for="(backend, index) in backends" :key="backend.title" :class="{ active: index === currentPosition }">
          <div class="projectDiv">
            <div class="projectContent">
              <div class="text-center">{{ backend.title }}</div>
              <img :src="`/new-portfolio${backend.image}`" alt="Project Image" class="" />
              <p class="mainP">Languages Used: <span class="mainS">{{ backend.language }}</span></p>
              <p class="mainP">Description: <span class="mainS">{{ backend.about }}</span></p>
              <a :href="backend.repo" class="" target="_blank">Github Repo</a>
            </div>
          </div>
        </div>
      </main>
    </div>
  </div>
  </div>
</template>

<style scoped>

.mainP {
  font-weight: bold;
}

.mainS {
  font-weight: normal;
}

.projectContent a {
  display: block;
  text-align: center;
  margin: 0 auto;
  /* z-index: 99; */
}


.mainProjDiv {
  border: 2px solid darkgoldenrod;
}

.mainProjectDivs {
  margin-top: 25px;
  min-height: 900px;
}

h3 {
  border: 1px dashed white;
  text-align: center;
}

img {
  height: 250px;
  width: 300px;
}

.bigBody {
  height: 600px;
  margin: 0;
  display: grid;
  grid-template-rows: 500px 100px;
  grid-template-columns: 1fr 30px 30px 30px 30px 30px 1fr;
  align-items: center;
  justify-items: center;
}

main#carousel1 {
  grid-row: 1 / 2;
  grid-column: 1 / 8;
  width: 100vw;
  height: 500px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  transform-style: preserve-3d;
  perspective: 600px;
  --items: 13;
  --middle: 3;
  --position: 1;
  pointer-events: none;
}

div.item {
  position: absolute;
  width: 300px;
  height: 400px;
  background-color: coral;
  --r: calc(var(--position) - var(--offset));
  --abs: max(calc(var(--r) * -1), var(--r));
  transition: all 0.25s linear;
  transform: rotateY(calc(-10deg * var(--r)))
    translateX(calc(-300px * var(--r)));
  z-index: calc((var(--position) - var(--abs)));
}


div.item:nth-of-type(1) {
  --offset: 1;
  background-color: #90f1ef;
}
div.item:nth-of-type(2) {
  --offset: 2;
  background-color: #ff70a6;
}
div.item:nth-of-type(3) {
  --offset: 3;
  background-color: #ff9770;
}
div.item:nth-of-type(4) {
  --offset: 4;
  background-color: #ffd670;
}
div.item:nth-of-type(5) {
  --offset: 5;
  background-color: #e9ff70;
}
div.item:nth-of-type(6) {
  --offset: 6;
  background-color: #a0ff70;
}

div.item:nth-of-type(7) {
  --offset: 7;
  background-color: #ffcc70;
}

div.item:nth-of-type(8) {
  --offset: 8;
  background-color: #70ffd6; 
}

div.item:nth-of-type(9) {
  --offset: 9;
  background-color: #ff70e9; 
}

div.item:nth-of-type(10) {
  --offset: 10;
  background-color: #70a0ff;
}

input:nth-of-type(1) {
  grid-column: 2 / 3;
  grid-row: 2 / 3;
}
input:nth-of-type(1):checked ~ main#carousel1 {
  --position: 1;
}

input:nth-of-type(2) {
  grid-column: 3 / 4;
  grid-row: 2 / 3;
}
input:nth-of-type(2):checked ~ main#carousel1 {
  --position: 2;
}

input:nth-of-type(3) {
  grid-column: 4 /5;
  grid-row: 2 / 3;
}
input:nth-of-type(3):checked ~ main#carousel1 {
  --position: 3;
}

input:nth-of-type(4) {
  grid-column: 5 / 6;
  grid-row: 2 / 3;
}
input:nth-of-type(4):checked ~ main#carousel1 {
  --position: 4;
}

input:nth-of-type(5) {
  grid-column: 6 / 7;
  grid-row: 2 / 3;
}
input:nth-of-type(5):checked ~ main#carousel1 {
  --position: 5;
}

input:nth-of-type(6) {
  grid-column: 2 / 3;
  grid-row: 3 / 3;
}

input:nth-of-type(6):checked ~ main#carousel1 {
  --position: 6;
}

input:nth-of-type(7) {
  grid-column: 3 / 4;
  grid-row: 3 / 3;
}

input:nth-of-type(7):checked ~ main#carousel1 {
  --position: 7;
}

input:nth-of-type(8) {
  grid-column: 4 / 5;
  grid-row: 3 / 3;
}

input:nth-of-type(8):checked ~ main#carousel1 {
  --position: 8;
}

input:nth-of-type(9) {
  grid-column: 5 / 6;
  grid-row: 3 / 3;
}

input:nth-of-type(9):checked ~ main#carousel1 {
  --position: 9;
}

input:nth-of-type(10) {
  grid-column: 6 / 7;
  grid-row: 3 / 3;
}

input:nth-of-type(10):checked ~ main#carousel1 {
  --position: 10;
}

</style>
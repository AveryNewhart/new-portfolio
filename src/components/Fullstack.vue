<script setup lang="ts">

import { ref } from 'vue';

const currentPosition = ref(0);

const updatePosition = (index: number) => {
  currentPosition.value = index;
};

interface Fullstack {
    title: string;
    image: string;
    deployed: string;
    language: string;
    about: string;
    repo: string;
}

const fullstacks: Fullstack[] = [
    {
        title: 'My Music',
        image: '/images/myMusic.png',
        deployed: 'https://my-music-4e69cad2a89f.herokuapp.com/',
        language: 'JavaScript, HTML, CSS',
        about: 'i love musiccccc this is the about section',
        repo: 'https://github.com/AveryNewhart/my-music',
    },
    {
        title: 'Your Movies',
        image: '/images/yourMovies.png',
        deployed: 'https://yourmovies.herokuapp.com/',
        language: 'JavaScript, HTML, CSS',
        about: 'i love moviessss this is the about section',
        repo: 'https://github.com/AveryNewhart/YOUR-MOVIES',
    },
    {
        title: 'The Flick Tracker',
        image: '/images/FlickTracker.png',
        deployed: 'https://the-flick-tracker.herokuapp.com/',
        language: 'JavaScript, HTML, CSS',
        about: 'i love movies oldddd this is the about section',
        repo: 'https://github.com/AveryNewhart/The-Flick-Tracker',
    },
    {
        title: 'The Tech Blog',
        image: '/images/techBlog.png',
        deployed: 'https://my-tech-blog-888.herokuapp.com/',
        language: 'JavaScript, HTML, CSS',
        about: 'i love blogging this is the about section',
        repo: 'https://github.com/AveryNewhart/Tech-Blog',
    },
];

</script>

<template>
  <div class="mainProjDiv">
  <div class="mainProjectDivs">
      <h3>Fullstack</h3>
    <div class="bigBody">
      <input type="radio" name="2position" v-for="(fullstack, index) in fullstacks" :key="fullstack.title" :id="'2position-' + index" @click="updatePosition(index)" />
      <main id="carousel2">
        <div class="item" v-for="(fullstack, index) in fullstacks" :key="fullstack.title" :class="{ active: index === currentPosition }">
          <div class="projectDiv">
            <div class="projectContent">
              <div class="text-center mt-2">{{ fullstack.title }}</div>
              <img :src="`/new-portfolio${fullstack.image}`" alt="Project Image" class="" />
              <p class="mainP">Languages Used: <span class="mainS">{{ fullstack.language }}</span></p>
              <p class="mainP">Description: <span class="mainS">{{ fullstack.about }}</span></p>
              <a :href="fullstack.repo" class="" target="_blank">Github Repo</a>
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

/* this is where i am styling the items in the carousel */
div.item {
    border-radius: 25px;
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

main#carousel2 {
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
input:nth-of-type(1):checked ~ main#carousel2 {
  --position: 1;
}

input:nth-of-type(2) {
  grid-column: 3 / 4;
  grid-row: 2 / 3;
}
input:nth-of-type(2):checked ~ main#carousel2 {
  --position: 2;
}

input:nth-of-type(3) {
  grid-column: 4 /5;
  grid-row: 2 / 3;
}
input:nth-of-type(3):checked ~ main#carousel2 {
  --position: 3;
}

input:nth-of-type(4) {
  grid-column: 5 / 6;
  grid-row: 2 / 3;
}
input:nth-of-type(4):checked ~ main#carousel2 {
  --position: 4;
}

input:nth-of-type(5) {
  grid-column: 6 / 7;
  grid-row: 2 / 3;
}
input:nth-of-type(5):checked ~ main#carousel2 {
  --position: 5;
}

input:nth-of-type(6) {
  grid-column: 2 / 3;
  grid-row: 3 / 3;
}

input:nth-of-type(6):checked ~ main#carousel2 {
  --position: 6;
}

input:nth-of-type(7) {
  grid-column: 3 / 4;
  grid-row: 3 / 3;
}

input:nth-of-type(7):checked ~ main#carousel2 {
  --position: 7;
}

input:nth-of-type(8) {
  grid-column: 4 / 5;
  grid-row: 3 / 3;
}

input:nth-of-type(8):checked ~ main#carousel2 {
  --position: 8;
}

input:nth-of-type(9) {
  grid-column: 5 / 6;
  grid-row: 3 / 3;
}

input:nth-of-type(9):checked ~ main#carousel2 {
  --position: 9;
}

input:nth-of-type(10) {
  grid-column: 6 / 7;
  grid-row: 3 / 3;
}

input:nth-of-type(10):checked ~ main#carousel2 {
  --position: 10;
}

</style>
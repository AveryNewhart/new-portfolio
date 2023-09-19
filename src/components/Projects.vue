<script setup lang="ts">

import { ref } from 'vue';

const currentPosition = ref(0);

const updatePosition = (index: number) => {
  currentPosition.value = index;
};

interface Frontend {
    title: string;
    image: string;
    deployed: string;
    language: string;
    about: string;
    repo: string;
}

const frontends: Frontend[] = [
    {
        title: 'Golf Lancaster',
        image: '/images/golfLancaster.png',
        deployed: 'https://averynewhart.github.io/golf-lancaster/',
        language: 'Vue, Typescript, Tailwind',
        about: 'i love gokfinggg this is the about section',
        repo: 'https://github.com/AveryNewhart/golf-lancaster',
    },
    {
        title: 'My Stopwatch',
        image: '/images/stopwatch.png',
        deployed: 'https://averynewhart.github.io/my-stopwatch/',
        language: 'Vue, Typescript, Tailwind',
        about: 'i love stopwacthes this is the about section',
        repo: 'https://github.com/AveryNewhart/my-stopwatch',
    },
    {
        title: 'Final Countdown',
        image: '/images/finalCountdown.png',
        deployed: 'https://averynewhart.github.io/final-countdown/',
        language: 'Vue, Typescript, Tailwind',
        about: 'i love counting down this is the about section',
        repo: 'https://github.com/AveryNewhart/final-countdown',
    },
    {
        title: 'Vue Calc',
        image: '/images/calc.png',
        deployed: 'https://averynewhart.github.io/vue-calc/',
        language: 'Vue, Typescript, Tailwind',
        about: 'i love math this is the about section',
        repo: 'https://github.com/AveryNewhart/vue-calc',
    },
    // {
    //     title: 'Note Taker',
    //     image: '/images/noteTaker.png',
    //     language: 'languages used here, js',
    //     about: 'i love taking notes this is the about section',
    //     repo: 'put repo link',
    // },
    {
        title: 'Timed Coding Quiz',
        image: '/images/codingQuiz.png',
        deployed: 'https://averynewhart.github.io/Timed-Coding-Quiz/index.html',
        language: 'HTML, CSS, JavaScript',
        about: 'i love quizzes this is the about section',
        repo: 'https://github.com/AveryNewhart/Timed-Coding-Quiz',
    },
    {
        title: 'Weather Forecast',
        image: '/images/weather.png',
        deployed: 'https://averynewhart.github.io/weather-forceast-dashbord/',
        language: 'HTML, CSS, JavaScript',
        about: 'i love weather this is the about section',
        repo: 'https://github.com/AveryNewhart/weather-forceast-dashbord',
    },
    {
        title: 'Password Generator',
        image: '/images/passwordGen.png',
        deployed: 'https://averynewhart.github.io/password-gen/',
        language: 'HTML, CSS, JavaScript',
        about: 'i love generating passwords this is the about section',
        repo: 'https://github.com/AveryNewhart/password-gen',
    },
    {
        title: 'Tic Tac Toe',
        image: '/images/tictactoe.png',
        deployed: 'https://averynewhart.github.io/tic-tac-toe/',
        language: 'TypeScript, HTML, CSS',
        about: 'i love tictactoe this is the about section',
        repo: 'https://github.com/AveryNewhart/tic-tac-toe',
    },
    {
        title: 'Track Your Time',
        image: '/images/trackYourDay.png',
        deployed: 'https://averynewhart.github.io/track-your-time/',
        language: 'TypeScript, HTML, CSS',
        about: 'i love to do lists this is the about section',
        repo: 'https://github.com/AveryNewhart/track-your-time',
    },
    {
        title: 'Musician Website',
        image: '/images/musicianWebsite.png',
        deployed: 'https://averynewhart.github.io/Musician-Website/',
        language: 'HTML, CSS',
        about: 'i love weather this is the about section',
        repo: 'https://github.com/AveryNewhart/Musician-Website',
    },
    // {
    //     title: 'Day Planner',
    //     image: '/images/dayPlanner.png',
    //     language: 'languages used here, html, css',
    //     about: 'i love planning my day this is the about section',
    //     repo: 'put repo link',
    // },
];

const totalFrontendProjects = ref(frontends.length);


</script>

<template>
  <div class="mainProjDiv">
  <div class="mainProjectDivs">
    <h3 class="mt-2">Frontend Projects</h3>
      <div class="bigBody">
        <input type="radio" name="position" v-for="(frontend, index) in frontends" :key="frontend.title" :id="'position-' + index" @click="updatePosition(index)" />
        <main id="carousel" :style="{ '--total-frontend-projects': totalFrontendProjects }">
          <div class="item" v-for="(frontend, index) in frontends" :key="frontend.title" :class="{ active: index === currentPosition }">
            <div class="projectDiv">
              <div class="projectContent">
                <div class="text-center mt-2 titleP">{{ frontend.title }}</div>
                <a :href="frontend.deployed" target="_blank">
              <img :src="`/new-portfolio${frontend.image}`" alt="Project Image" class="" />
            </a>
                <p class="mainP">Languages Used: <span class="mainS">{{ frontend.language }}</span></p>
                <p class="mainP">Description: <span class="mainS">{{ frontend.about }}</span></p>
                <a :href="frontend.repo" class="linkSite" target="_blank">Github Repo</a>
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

.titleP {
  font-weight: bold;
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
  /* margin-top: 25px; */
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

main#carousel {
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
input:nth-of-type(1):checked ~ main#carousel {
  --position: 1;
}

input:nth-of-type(2) {
  grid-column: 3 / 4;
  grid-row: 2 / 3;
}
input:nth-of-type(2):checked ~ main#carousel {
  --position: 2;
}

input:nth-of-type(3) {
  grid-column: 4 /5;
  grid-row: 2 / 3;
}
input:nth-of-type(3):checked ~ main#carousel {
  --position: 3;
}

input:nth-of-type(4) {
  grid-column: 5 / 6;
  grid-row: 2 / 3;
}
input:nth-of-type(4):checked ~ main#carousel {
  --position: 4;
}

input:nth-of-type(5) {
  grid-column: 6 / 7;
  grid-row: 2 / 3;
}
input:nth-of-type(5):checked ~ main#carousel {
  --position: 5;
}

input:nth-of-type(6) {
  grid-column: 2 / 3;
  grid-row: 3 / 3;
}

input:nth-of-type(6):checked ~ main#carousel {
  --position: 6;
}

input:nth-of-type(7) {
  grid-column: 3 / 4;
  grid-row: 3 / 3;
}

input:nth-of-type(7):checked ~ main#carousel {
  --position: 7;
}

input:nth-of-type(8) {
  grid-column: 4 / 5;
  grid-row: 3 / 3;
}

input:nth-of-type(8):checked ~ main#carousel {
  --position: 8;
}

input:nth-of-type(9) {
  grid-column: 5 / 6;
  grid-row: 3 / 3;
}

input:nth-of-type(9):checked ~ main#carousel {
  --position: 9;
}

input:nth-of-type(10) {
  grid-column: 6 / 7;
  grid-row: 3 / 3;
}

input:nth-of-type(10):checked ~ main#carousel {
  --position: 10;
}

</style>
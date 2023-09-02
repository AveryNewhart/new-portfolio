<script setup lang="ts">

import { ref } from 'vue';

interface Frontend {
    title: string;
    image: string;
    language: string;
    about: string;
    repo: string;
}

const frontends: Frontend[] = [
    {
        title: 'Golf Lancaster',
        image: '/images/golfLancaster.png',
        language: 'languages used here, vue',
        about: 'i love gokfinggg this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'My Stopwatch',
        image: '/images/stopwatch.png',
        language: 'languages used here, vue',
        about: 'i love stopwacthes this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Final Countdown',
        image: '/images/finalCountdown.png',
        language: 'languages used here, vue',
        about: 'i love counting down this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Vue Calc',
        image: '/images/calc.png',
        language: 'languages used here, vue',
        about: 'i love math this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Free Blackjack',
        image: 'put an under construction picture here',
        language: 'languages used here, js',
        about: 'i love blackjack this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Note Taker',
        image: '/images/noteTaker.png',
        language: 'languages used here, js',
        about: 'i love taking notes this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Timed Coding Quiz',
        image: '/images/codingQuiz.png',
        language: 'languages used here, js',
        about: 'i love quizzes this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Weather Forecast',
        image: '/images/weather.png',
        language: 'languages used here, js',
        about: 'i love weather this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Password Generator',
        image: '/images/passwordGen.png',
        language: 'languages used here, js',
        about: 'i love generating passwords this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Tic Tac Toe',
        image: '/images/tictactoe.png',
        language: 'languages used here, ts',
        about: 'i love tictactoe this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Track Your Time',
        image: '/images/trackYourDay.png',
        language: 'languages used here, ts',
        about: 'i love to do lists this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Musician Website',
        image: '/images/musicianWebsite.png',
        language: 'languages used here, html, css',
        about: 'i love weather this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Day Planner',
        image: '/images/dayPlanner.png',
        language: 'languages used here, html, css',
        about: 'i love planning my day this is the about section',
        repo: 'put repo link',
    },
];

const currentPosition = ref(0);

const updatePosition = (index: number) => {
  currentPosition.value = index;
};

interface Backend {
    title: string;
    image: string;
    language: string;
    about: string;
    repo: string;
}

const backends: Backend[] = [
    {
        title: 'README Generator',
        image: '/images/readMeGen.png',
        language: 'languages used here',
        about: 'i love creating read meeeeeeeeesssss about section',
        repo: 'put repo link',
    },
    {
        title: 'Social Network Backend',
        image: '/images/socialNetworkBackend.png',
        language: 'languages used here, js',
        about: 'i love social netowrking about section',
        repo: 'put repo link',
    },
    {
        title: 'E-Commerce Site',
        image: '/images/eCommerce.png',
        language: 'languages used here, js',
        about: 'i love ecommerceeee about section',
        repo: 'put repo link',
    },
    {
        title: 'Employee Tracker',
        image: '/images/employeeTracker.png',
        language: 'languages used here, js',
        about: 'i love tracking employeeeeees about section',
        repo: 'put repo link',
    },
    {
        title: 'Team Profile Generator',
        image: '/images/teamProfGen.png',
        language: 'languages used here, js',
        about: 'i love creating team profiles about section',
        repo: 'put repo link',
    },
];

interface Fullstack {
    title: string;
    image: string;
    language: string;
    about: string;
    repo: string;
}

const fullstacks: Fullstack[] = [
    {
        title: 'My Music',
        image: '/images/myMusic.png',
        language: 'languages used here',
        about: 'i love musiccccc this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'Your Movies',
        image: '/images/yourMovies.png',
        language: 'languages used here',
        about: 'i love moviessss this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'The Flick Tracker',
        image: '/images/FlickTracker.png',
        language: 'languages used here',
        about: 'i love movies oldddd this is the about section',
        repo: 'put repo link',
    },
    {
        title: 'The Tech Blog',
        image: '/images/techBlog.png',
        language: 'languages used here',
        about: 'i love blogging this is the about section',
        repo: 'put repo link',
    },
];

</script>

<template>
  <div class="mainProjDiv">
    <h1>Projects</h1>
    <p>for projects i want to make it into three seperate sections, frontend, backend, and fullstack</p>

    <div class="bigBody">
      <h3>Frontend</h3>
    <input type="radio" name="position" v-for="(frontend, index) in frontends" :key="frontend.title" :id="'position-' + index" @click="updatePosition(index)" />
    <main id="carousel">
      <div class="item" v-for="(frontend, index) in frontends" :key="frontend.title" :class="{ active: index === currentPosition }">
        <div class="projectDiv">
          <div class="projectContent">
            <div class="">{{ frontend.title }}</div>
            <img :src="`/new-portfolio${frontend.image}`" alt="Project Image" class="" />
            <p class="">Languages Used: <span class="">{{ frontend.language }}</span></p>
            <p class="">Description: <span class="">{{ frontend.about }}</span></p>
            <a :href="frontend.repo" class="" target="_blank">Github Repo</a>
          </div>
        </div>
      </div>
    </main>
  </div>

  <div class="bigBody">
      <h3>Backend</h3>
    <input type="radio" name="position" v-for="(backend, index) in backends" :key="backend.title" :id="'position-' + index" @click="updatePosition(index)" />
    <main id="carousel">
      <div class="item" v-for="(backend, index) in backends" :key="backend.title" :class="{ active: index === currentPosition }">
        <div class="projectDiv">
          <div class="projectContent">
            <div class="">{{ backend.title }}</div>
            <img :src="`/new-portfolio${backend.image}`" alt="Project Image" class="" />
            <p class="">Languages Used: <span class="">{{ backend.language }}</span></p>
            <p class="">Description: <span class="">{{ backend.about }}</span></p>
            <a :href="backend.repo" class="" target="_blank">Github Repo</a>
          </div>
        </div>
      </div>
    </main>
  </div>

  <div class="bigBody">
      <h3>Fullstack</h3>
    <input type="radio" name="position" v-for="(fullstack, index) in fullstacks" :key="fullstack.title" :id="'position-' + index" @click="updatePosition(index)" />
    <main id="carousel">
      <div class="item" v-for="(fullstack, index) in fullstacks" :key="fullstack.title" :class="{ active: index === currentPosition }">
        <div class="projectDiv">
          <div class="projectContent">
            <div class="">{{ fullstack.title }}</div>
            <img :src="`/new-portfolio${fullstack.image}`" alt="Project Image" class="" />
            <p class="">Languages Used: <span class="">{{ fullstack.language }}</span></p>
            <p class="">Description: <span class="">{{ fullstack.about }}</span></p>
            <a :href="fullstack.repo" class="" target="_blank">Github Repo</a>
          </div>
        </div>
      </div>
    </main>
  </div>
  </div>
</template>

<style scoped>

.mainProjDiv {
  border: 2px solid darkgoldenrod;
}

h3 {
  border: 1px dashed white;
}

img {
  height: 250px;
  width: 250px;
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
  --items: 5;
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

</style>
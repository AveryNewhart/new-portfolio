<script setup lang="ts">

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
    <div>
      <h3>Frontend</h3>
    <div v-for="frontend in frontends" :key="frontend.title" class="">
      <div class="projectDiv">
        <div class="projectContent">
            <div class="">
                {{ frontend.title }}
            </div>
          <img :src="`/new-portfolio${frontend.image}`" alt="Project Image" class="" />
          <p class="">Languages Used:  <span class="">{{ frontend.language }}</span></p>
          <p class="">Description: <span class="">{{ frontend.about }}</span></p>
          <a :href="frontend.repo" class="" target="_blank">Github Repo</a>
        </div>
      </div>
    </div>
    </div>
    <div>
      <h3>Backend</h3>
      <p>for this section, make the image clickable and take you to the video demo</p>
    <div v-for="backend in backends" :key="backend.title" class="">
      <div class="projectDiv">
        <div class="projectContent">
            <div class="">
                {{ backend.title }}
            </div>
          <img :src="`/new-portfolio${backend.image}`" alt="Project Image" class="" />
          <p class="">Languages Used:  <span class="">{{ backend.language }}</span></p>
          <p class="">Description: <span class="">{{ backend.about }}</span></p>
          <a :href="backend.repo" class="" target="_blank">Github Repo</a>
        </div>
      </div>
    </div>
    </div>
    <div>
      <h3>Fullstack</h3>
    <div v-for="fullstack in fullstacks" :key="fullstack.title" class="">
      <div class="projectDiv">
        <div class="projectContent">
            <div class="">
                {{ fullstack.title }}
            </div>
          <img :src="`/new-portfolio${fullstack.image}`" alt="Project Image" class="" />
          <p class="">Languages Used:  <span class="">{{ fullstack.language }}</span></p>
          <p class="">Description: <span class="">{{ fullstack.about }}</span></p>
          <a :href="fullstack.repo" class="" target="_blank">Github Repo</a>
        </div>
      </div>
    </div>
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

</style>
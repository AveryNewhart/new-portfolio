<script setup lang="ts">


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
        image: '/images/newGolf.png',
        deployed: 'https://averynewhart.github.io/golf-lancaster/',
        language: 'Vue, Typescript, Tailwind',
        about: 'I got tired of looking up every golf course and trying to find their rates so I had an idea on how to fix that. Here you can, find all the golf courses and their rates in Lancaster County, Pennsylvania... all in one place.',
        repo: 'https://github.com/AveryNewhart/golf-lancaster',
    },
    {
        title: 'My Stopwatch',
        image: '/images/stopwatch.png',
        deployed: 'https://averynewhart.github.io/my-stopwatch/',
        language: 'Vue, Typescript, Tailwind',
        about: 'This is a simple easy to use stopwatch with a start, stop, and restart button.',
        repo: 'https://github.com/AveryNewhart/my-stopwatch',
    },
    {
        title: 'Final Countdown',
        image: '/images/finalCountdown.png',
        deployed: 'https://averynewhart.github.io/final-countdown/',
        language: 'Vue, Typescript, Tailwind',
        about: 'This is a simple easy to use timer that you can set hours, minutes, and seconds.',
        repo: 'https://github.com/AveryNewhart/final-countdown',
    },
    {
        title: 'Vue Calc',
        image: '/images/ndwCalc.png',
        deployed: 'https://averynewhart.github.io/vue-calc/',
        language: 'Vue, Typescript, Tailwind',
        about: 'This is an easy to use calculator. It has all of the basic functions.',
        repo: 'https://github.com/AveryNewhart/vue-calc',
    },
    {
        title: 'Note Taker',
        image: '/images/newNoteTaker.png',
        deployed: 'https://note-take-88-99.herokuapp.com/',
        language: 'HTML, CSS, JavaScript',
        about: 'Here you will be able to write notes and save them to go back to anytime.',
        repo: 'https://github.com/AveryNewhart/Note-Taker',
    },
    // {
    //     title: 'Timed Coding Quiz',
    //     image: '/images/codingQuiz.png',
    //     deployed: 'https://averynewhart.github.io/Timed-Coding-Quiz/index.html',
    //     language: 'HTML, CSS, JavaScript',
    //     about: 'Simple coding quiz app. It is timed and your time adds to your score. Become the best!',
    //     repo: 'https://github.com/AveryNewhart/Timed-Coding-Quiz',
    // },
    {
        title: 'Weather Forecast',
        image: '/images/weather.png',
        deployed: 'https://averynewhart.github.io/weather-forceast-dashbord/',
        language: 'HTML, CSS, JavaScript',
        about: 'This is a simple weather app. Search up any city for the forecast.',
        repo: 'https://github.com/AveryNewhart/weather-forceast-dashbord',
    },
    {
        title: 'Password Generator',
        image: '/images/passwordGen.png',
        deployed: 'https://averynewhart.github.io/password-gen/',
        language: 'HTML, CSS, JavaScript',
        about: 'Have you ever been unsure of what to make a password. Use this simple password generator.',
        repo: 'https://github.com/AveryNewhart/password-gen',
    },
    {
        title: 'Tic Tac Toe',
        image: '/images/tictactoe.png',
        deployed: 'https://averynewhart.github.io/tic-tac-toe/',
        language: 'TypeScript, HTML, CSS',
        about: 'Tic Tac Toe game which keeps track of each players wins!',
        repo: 'https://github.com/AveryNewhart/tic-tac-toe',
    },
    {
        title: 'Track Your Time',
        image: '/images/trackYourDay.png',
        deployed: 'https://averynewhart.github.io/track-your-time/',
        language: 'TypeScript, HTML, CSS',
        about: 'This is a simple to-do list. Click on each item to cross it off.',
        repo: 'https://github.com/AveryNewhart/track-your-time',
    },
    {
        title: 'Musician Website',
        image: '/images/newMusicSite.png',
        deployed: 'https://averynewhart.github.io/Musician-Website/',
        language: 'HTML, CSS, JavaScript',
        about: 'This is a basic template I made that can be used for any musician, or any public person. It has tour, about, and store pages.',
        repo: 'https://github.com/AveryNewhart/Musician-Website',
    },
    {
        title: 'Day Planner',
        image: '/images/newDay.png',
        deployed: 'https://averynewhart.github.io/Day-Planner/',
        language: 'HTML, CSS, JavaScript',
        about: 'Plan out your whole day by the hour, the time of the day also reflects which color each hour is.',
        repo: 'https://github.com/AveryNewhart/Day-Planner',
    },
];


</script>

<template>
  <div class="text-center">
      <div class="mainHead">
          <h1 class="mt-2 projectH1">Frontend Projects</h1>
      </div>
    <div class="mainProjectDivs">
      <div class="projectGrid">
        <div class="projectDiv" v-for="(frontend, index) in frontends" :key="index">
          <div class="projectContent">
            <div class="text-center mt-2 titleP">
              <h2>{{ frontend.title }}</h2>
          </div>
            <img :src="`${frontend.image}`" alt="Project Image" class="projectImage" />
            <p class="mainP">Languages Used: <span class="mainS">{{ frontend.language }}</span></p>
            <p class="mainPD">Description: <span class="mainSA">{{ frontend.about }}</span></p>
            <a :href="frontend.repo" class="projectLink" target="_blank">Github Repo</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.mainP {
  font-weight: bold;
  font-size: 35px;
  font-family: 'Gaegu';
  margin-top: 10px;
  background-color: rgba(255, 255, 255, 0.3); /* Brighter background with the same translucency */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect */
  border-radius: 10px;
}

.projectH1 {
  text-decoration: dashed underline white;
}

.mainPD {
    font-weight: bold;
    font-size: 35px;
    font-family: 'Gaegu';
    margin-top: 10px;
    height: 150px;
    overflow: scroll;
    background-color: rgba(255, 255, 255, 0.3); /* Brighter background with the same translucency */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect */
  border-radius: 10px;
  }

.mainS {
  font-weight: normal;
  font-size: 30px;
}

.mainSA {
  font-weight: normal;
  font-size: 25px;
}

.titleP {
  font-weight: bold;
  font-family: 'Gaegu';
  font-size: 35px;
    text-decoration: dashed underline white;
}

.projectContent a {
  display: block;
  text-align: center;
  margin: 0 auto;
}

.mainProjectDivs {
  margin-top: 25px;
  min-height: 900px;
  margin-bottom: 15px
}


.mainHead {
  display: inline-block; /* This makes the container size to its content */
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  border-radius: 20px;
  font-size: 45px;
  font-family: 'Gaegu';
  margin-top: 15px;
}

.projectImage {
  /* height: 300px; */
  /* width: 450px;  */
  border-radius: 10px;
  border: 2px solid white;
}

.projectLink {
  /* background-color: linear-gradient(315deg, rgb(29, 255, 25) 3%, rgba(48, 238, 226, 1) 38%, rgba(60, 132, 206, 1) 68%, rgba(101, 0, 94, 1) 98%);  */
  background-color: rgba(255, 255, 255, 0.3); /* Brighter background with the same translucency */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect */
  border-radius: 10px;
  border: 2px solid white;
  font-family: 'Gaegu';
  font-size: 1.5rem;
  padding: 5px;
  margin-top: 20px;
  transform: scale(.9);
}

.projectLink:hover {
  background-image: linear-gradient(30deg,#f5b6b3,#6272fc);
  transform: scale(0.7);
  transition-duration: 1s ease-out;
  /* box-shadow: #030557 0px 25px 35px -13px; */
  color:#ffffeb;
  border:0.1px  #6e0175;
  -webkit-tap-highlight-color: transparent;
  animation-play-state: paused;
}


.projectGrid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* three projects per row */
  gap: 20px; /* the gap between projects */
  margin-top: 20px;
}

@media (max-width: 768px) {
  .projectGrid {
    grid-template-columns: 1fr; /* one project per row on mobile */
  }
}

/* Styles for each project */
.projectDiv {
  background-color: transparent; 
  border: 5px solid white;
  border-radius: 25px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
  text-align: center;
}

.mainPD .mainP .mainS .mainSA {
  font-size: 45px;
}

</style>
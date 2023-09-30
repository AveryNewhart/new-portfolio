<script setup lang="ts">

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
    <div class="text-center">
        <div class="mainHead">
            <h1 class="mt-2">Backend Projects</h1>
        </div>
      <div class="mainProjectDivs">
        <div class="projectGrid">
          <div class="projectDiv" v-for="(backend, index) in backends" :key="index">
            <div class="projectContent">
              <div class="text-center mt-2 titleP">
                <h2>{{ backend.title }}</h2>
            </div>
              <img :src="`/new-portfolio${backend.image}`" alt="Project Image" class="projectImage" />
              <p class="mainP">Languages Used: <span class="mainS">{{ backend.language }}</span></p>
              <p class="mainP">Description: <span class="mainSA">{{ backend.about }}</span></p>
              <a :href="backend.repo" class="projectLink" target="_blank">Github Repo</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <style scoped>
  .mainP {
    font-weight: bold;
    font-size: 20px;
    font-family: 'Gaegu';
    margin-top: 10px;
  }
  
  .mainS {
    font-weight: normal;
    font-size: 15px;
  }
  
  .mainSA {
    font-weight: normal;
    font-size: 15px;
  }
  
  .titleP {
    font-weight: bold;
    font-family: 'Gaegu';
    font-size: 25px;
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
    /* height: 300px;
    width: 350px;  */
    border-radius: 10px;
    border: 2px solid white;
  }

  .projectLink {
    background-color: linear-gradient(315deg, rgb(29, 255, 25) 3%, rgba(48, 238, 226, 1) 38%, rgba(60, 132, 206, 1) 68%, rgba(101, 0, 94, 1) 98%); 
    border-radius: 10px;
    border: 2px solid white;
    font-family: 'Gaegu';
    font-size: 1.5rem;
    padding: 10px;
    margin-top: 10px;
  }

  .projectLink:hover {
    background-image: linear-gradient(30deg,#f5b6b3,#6272fc);
    transform: scale(0.9);
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
  
  </style>
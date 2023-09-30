<script setup lang="ts">


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
    <div class="text-center">
        <div class="mainHead">
            <h1 class="mt-2">Fullstack Projects</h1>
        </div>
      <div class="mainProjectDivs">
        <div class="projectGrid">
          <div class="projectDiv" v-for="(fullstack, index) in fullstacks" :key="index">
            <div class="projectContent">
              <div class="text-center mt-2 titleP">
                <h2>{{ fullstack.title }}</h2>
            </div>
              <img :src="`/new-portfolio${fullstack.image}`" alt="Project Image" class="projectImage" />
              <p class="mainP">Languages Used: <span class="mainS">{{ fullstack.language }}</span></p>
              <p class="mainP">Description: <span class="mainSA">{{ fullstack.about }}</span></p>
              <a :href="fullstack.repo" class="projectLink" target="_blank">Github Repo</a>
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
  
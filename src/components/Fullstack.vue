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
    <div class="mainProjDiv">
      <div class="mainProjectDivs">
        <h3 class="mt-2">Fullstack Projects</h3>
        <div class="projectGrid">
          <div class="projectDiv" v-for="(fullstack, index) in fullstacks" :key="index">
            <div class="projectContent">
              <div class="text-center mt-2 titleP">{{ fullstack.title }}</div>
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
    font-size: 1rem;
    color: #333;
  }
  
  .mainS {
    font-weight: normal;
  }
  
  .mainSA {
    font-weight: normal;
    font-size: .90rem;
  }
  
  .titleP {
    font-weight: bold;
  }
  
  .projectContent a {
    display: block;
    text-align: center;
    margin: 0 auto;
  }
  
  .mainProjectDivs {
    margin-top: 25px;
    min-height: 900px;
  }
  
  h3 {
    text-align: center;
    color: #333;
    font-size: 1.5rem;
  }
  
  img.projectImage {
    height: 300px;
    width: 350px; 
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
  
  .projectLink {
    color: white;
    text-decoration: none;
    background-color: #333;
    padding: 10px 20px;
    border-radius: 5px;
    display: inline-block;
    margin-top: 10px;
  }
  
  .projectLink:hover {
    background-color: #555;
  }
  </style>
  
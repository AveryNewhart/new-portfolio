<script setup lang="ts">

interface Project {
    title: string;
    image: string;
    language: string;
    about: string;
    repo: string;
}

const projects: Project[] = [
    {
        title: 'My Music',
        image: 'put path here and make image clickable to take user to deployed app',
        language: 'languages used here',
        about: 'i love musiccccc this is the about section',
        repo: 'put repo link',
    },
];

</script>

<template>
  <div>
    <h1>Projects</h1>
    <div v-for="project in projects" :key="project.title" class="">
      <div class="projectDiv">
        <div class="projectContent">
            <div class="">
                {{ project.title }}
            </div>
          <!-- <img :src="`/new-portfolio${project.image}`" alt="Project Image" class="" /> -->
          <p> image is gonna be here, uncomment code {{ project.image }}</p>
          <p class="">Languages Used:  <span class="">{{ project.language }}</span></p>
          <p class="">Description: <span class="">{{ project.about }}</span></p>
          <a :href="project.repo" class="" target="_blank">Github Repo</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
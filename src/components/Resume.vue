<script setup lang="ts">
</script>

<template>
  <div class="mainResDiv">
    <h1 class="text-3xl font-semibold mb-4">Resume</h1>
    <div class="skills-section">
      <div class="md:flex">
        <!-- Frontend Skills -->
        <div class="md:w-1/2 mb-4 md:mb-0">
          <h2 class="text-xl font-semibold mb-2 text-center">Frontend Skills</h2>
          <ul>
            <li class="skill">
              <!-- <img src="/images/frontend-icon1.png" alt="Frontend Skill 1" class="w-12 h-12" /> -->
              <p>Frontend Skill 1</p>
            </li>
            <li class="skill">
              <!-- <img src="/images/frontend-icon2.png" alt="Frontend Skill 2" class="w-12 h-12" /> -->
              <p>Frontend Skill 2</p>
            </li>
            <!-- Add more frontend skills as list items -->
          </ul>
        </div>
        <!-- Backend Skills -->
        <div class="md:w-1/2">
          <h2 class="text-xl font-semibold mb-2 text-center">Backend Skills</h2>
          <ul>
            <li class="skill">
              <!-- <img src="/images/backend-icon1.png" alt="Backend Skill 1" class="w-12 h-12" /> -->
              <p>Backend Skill 1</p>
            </li>
            <li class="skill">
              <!-- <img 
              src="/images/backend-icon2.png" alt="Backend Skill 2" class="w-12 h-12" /> -->
              <p>Backend Skill 2</p>
            </li>
            <!-- Add more backend skills as list items -->
          </ul>
        </div>
      </div>
    </div>
    <a 
    href="/new-portfolio/myNewResumeAveryNewhart.pdf" 
    class="text-blue-500 hover:underline">Download Resume (PDF)</a>
  </div>
</template>

<style scoped>
.mainResDiv {
  border: 2px solid silver;
  padding: 20px;
  height: 900px;
}

.skills-section {
}

.skill {
  text-align: center;
  list-style: none;
  margin-bottom: 5px;
}


@media (max-width: 768px) {
  .md:flex {
    flex-direction: column; 
  }
}
</style>


<!-- <template>
  <div class="mainResDiv">
    <h1>Resume</h1>
    <p>make this more of a skills section</p>
    <p>have two sections, one for frontend and one of backend</p>
    <p>with each skill i want to have a small image/icon associated with it. </p>
    <p>then ofcourse have my resume available to download</p>
  </div>
</template>

<style scoped>

.mainResDiv {
  border: 2px solid silver;
}

</style> -->
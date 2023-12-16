<script setup lang="ts">

/* fontawesome core */
import { library } from '@fortawesome/fontawesome-svg-core'

/* free styles */
import { faTwitter } from '@fortawesome/free-brands-svg-icons'
import { faGithub } from '@fortawesome/free-brands-svg-icons'
import { faLinkedin } from '@fortawesome/free-brands-svg-icons'



/* add each imported icon to the library */
library.add(faTwitter, faGithub, faLinkedin)

</script>

<template>
  <div class="mainDivFoot">  
    <div class="wave-border"></div> 
    <footer class="flex justify-center">
      <div class="p-4 md:flex md:items-center md:justify-between">
        <ul class="flex justify-center flex-wrap items-center text-sm font-medium sm:mt-0">
          <li class="icons">
            <a href="https://github.com/AveryNewhart" target="_blank" class="mr-4 icons"><font-awesome-icon :icon="['fab', 'github']" style="color: #925ff0;" /></a>
          </li>
          <li class="icons">
            <a href="https://www.linkedin.com/in/avery-newhart-0654a9263/" target="_blank" class="mr-4 icons"><font-awesome-icon :icon="['fab', 'linkedin']" style="color: #925ff0;" /></a>
          </li>
          <li class="icons">
            <a href="https://twitter.com/CodingWithAvery" target="_blank" class="mr-4 icons"><font-awesome-icon :icon="['fab', 'twitter']" style="color: #925ff0;" /></a>
          </li>
        </ul>
      </div>
    </footer>
  </div>
</template>


<style scoped>

.mainDivFoot {
  /* border-top: 5px solid white; */
  position: relative;
}

.icons {
  font-size: 30px;
  margin-left: 10px;
  margin-right: 10px;
}

.wave-border {
  width: 100%;
  height: 5px;
  position: absolute;
  top: 0;
  left: 0;
  overflow: hidden;
}

.wave-border::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 5px;
  top: 0;
  background: linear-gradient(to right, #925ff0, #a3fda1);
  animation: wave 2s infinite;
}

@keyframes wave {
  0%, 100% {
    background-position: 0 0;
  }
  50% {
    background-position: 100% 0;
  }
}

</style>
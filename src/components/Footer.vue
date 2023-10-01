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
    <footer class="flex justify-center">
      <div class="p-4 md:flex md:items-center md:justify-between">
        <ul class="flex justify-center flex-wrap items-center text-sm font-medium sm:mt-0">
          <li class="icons">
            <a href="https://github.com/AveryNewhart" target="_blank" class="mr-4 icons"><font-awesome-icon :icon="['fab', 'github']" /></a>
          </li>
          <li class="icons">
            <a href="https://www.linkedin.com/in/avery-newhart-0654a9263/" target="_blank" class="mr-4 icons"><font-awesome-icon :icon="['fab', 'linkedin']" /></a>
          </li>
          <li class="icons">
            <a href="https://twitter.com/CodingWithAvery" target="_blank" class="mr-4 icons"><font-awesome-icon :icon="['fab', 'twitter']" /></a>
          </li>
        </ul>
      </div>
    </footer>
  </div>
</template>


<style scoped>

.mainDivFoot {
  border-top: 5px solid white;
}

.icons {
  font-size: 30px;
  margin-left: 10px;
  margin-right: 10px;
}

</style>
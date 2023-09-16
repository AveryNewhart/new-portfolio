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
          <li>
            <a href="" class="mr-4"><font-awesome-icon :icon="['fab', 'github']" fade /></a>
          </li>
          <li>
            <a href="" class="mr-4"><font-awesome-icon :icon="['fab', 'linkedin']" fade /></a>
          </li>
          <li>
            <a href="" class="mr-4"><font-awesome-icon :icon="['fab', 'twitter']" fade /></a>
          </li>
        </ul>
      </div>
    </footer>
  </div>
</template>


<style scoped>

.mainDivFoot {
  border-top: 5px solid black;
}

</style>
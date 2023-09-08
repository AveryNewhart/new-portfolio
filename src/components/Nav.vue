<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      showMenu: false,
    };
  },

methods: {
    navigateTo(sectionId: string) {
      this.$emit('navigate', sectionId); // Emit a custom event with the sectionId
    },
  },
});
</script>



<template>
  <div>
    <div class="mainDivNav">
      <nav
        class="
          container
          px-4
          py-5
          mx-auto
          md:flex md:justify-between md:items-center
        "
      >
        <div class="flex items-center justify-between">
          <div
            class="
              text-xl
              font-bold
              md:text-2xl
            "
            >Avery Newhart
        </div>
          <!-- Mobile menu button -->
          <div @click="showMenu = !showMenu" class="flex md:hidden">
            <!-- adjust colors of hover when i decide exact colors i want to use -->
            <button
              type="button"
              class="
                hover:text-gray-400
                focus:outline-none focus:text-gray-400
              "
            >
              <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
                <path
                  fill-rule="evenodd"
                  d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
                ></path>
              </svg>
            </button>
          </div>
        </div>

        <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
        <ul
          :class="showMenu ? 'flex' : 'hidden'"
          class="
            flex-col
            mt-8
            space-y-4
            md:flex
            md:space-y-0
            md:flex-row
            md:items-center
            md:space-x-10
            md:mt-0
          "
        >
          <li class="text-sm font-bold hover:text-blue-400">
            <a @click="navigateTo('about1')" class="">About</a>
          </li>
          <li class="text-sm font-bold hover:text-blue-400">
            <a @click="navigateTo('projects1')" class="">Projects</a>
          </li>
          <li class="text-sm font-bold hover:text-blue-400">
            <a @click="navigateTo('resume1')" class="">Resume</a>
          </li>
          <li class="text-sm font-bold hover:text-blue-400">
            <a @click="navigateTo('contact1')" class="">Contact</a>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</template>

<style scoped>

.mainDivNav {
  border-bottom: 5px solid black;
}

</style>
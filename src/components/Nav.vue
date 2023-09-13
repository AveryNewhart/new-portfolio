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
            <a @click="navigateTo('about1')" class="navBut">About</a>
          </li>
          <li class="text-sm font-bold hover:text-blue-400">
            <a @click="navigateTo('projects1')" class="navBut">Projects</a>
          </li>
          <li class="text-sm font-bold hover:text-blue-400">
            <a @click="navigateTo('resume1')" class="navBut">Resume</a>
          </li>
          <li class="text-sm font-bold hover:text-blue-400">
            <a @click="navigateTo('contact1')" class="navBut">Contact</a>
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

.navBut {
  padding: 10px;
  font: 25px;
  color:#ffff;
  border-radius:20px;
  background-image: linear-gradient(40deg,#d38cff,#6272fc);
  box-shadow: rgba(50, 50, 93, 1) 0px 50px 100px -20px, rgba(0, 0, 0, 0.5) 0px 30px 60px -30px, rgba(10, 37, 64, 0.65) 0px -2px 6px 0px inset;
  cursor:pointer;
  transform: scale(0.8);
  transition: all .2s ease-out;
}

.navBut:hover{
  background-image: linear-gradient(30deg,#f5b6b3,#6272fc);
  transform: scale(0.9);
  transition-duration: 1s ease-out;
  box-shadow: #030557 0px 25px 35px -13px;
  border-radius:15px;
  color:#ffffeb;
  border:0.1px  #6e0175;
  -webkit-tap-highlight-color: transparent;
  animation-play-state: paused;
}
.navBut:after{
  animation-play-state: paused;
}

@keyframes shine {
  0% {
    transform: translateX(-30px) rotate(-25deg);
  }
  
  100% {
    transform: translateX(250px) rotate(-25deg);
  }
}






@media only screen and (max-width:600px){
  body{
  background-color:white;
}
.navBut{
  list-style:none;
  margin: 0px;
  padding: 10px 20px;
  font-size: 0.8rem;
  font-family:bolder;
  font-family:"Monaco";
  color:#ffff;
  border-radius:16px;
  background-image: linear-gradient(40deg,#d38cff,#6272fc);
  box-shadow: rgba(50, 50, 93, 1) 0px 50px 100px -20px, rgba(0, 0, 0, 0.5) 0px 30px 60px -30px, rgba(10, 37, 64, 0.65) 0px -2px 6px 0px inset;
  cursor:pointer;
  transform: scale(0.8);
  transition: all .2s ease-in-out;
}
.navBut{
  display:flex;
  justify-content:center;
}
.navBut{
  margin-top:5rem;
  margin-left:-2rem
}

.navBut:hover{
  background-image: linear-gradient(30deg,#f5b6b3,#6272fc);
  font-size: 0.8rem;
  transform: scale(0.9);
  transition-duration: 1s ease-out;
  box-shadow: #030557 0px 25px 35px -5px;
  border-radius:13px;
  color:#ffffeb;
  border:0.1px  #6e0175;
  animation-play-state: paused;
/*   font-family:"Monaco" */
}
  .navBut:hover::after{
    animation-play-state: paused;
  }

}

</style>
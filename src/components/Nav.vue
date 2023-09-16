<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      showMenu: false,
      dropdownOpen: false,
    };
  },

methods: {
    navigateTo(sectionId: string) {
      this.$emit('navigate', sectionId); // Emit a custom event with the sectionId
    },
    toggleDropdown() {
      this.dropdownOpen = !this.dropdownOpen;
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
              myName
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
          <!-- <li class="text-sm font-bold hover:text-blue-400">
            <a @click="navigateTo('projects1')" class="navBut">Projects</a>
          </li> -->
          <li class="group text-sm font-bold hover:text-blue-400">
            <button @click="toggleDropdown" class="navBut dropdown-button">
              Projects
              <svg
                class="w-4 h-4 ml-2 transform group-hover:rotate-180 transition-transform"
                :class="{ 'rotate-180': dropdownOpen }"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  d="M6.293 6.293a1 1 0 011.414 0L10 8.586l2.293-2.293a1 1 0 111.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                ></path>
              </svg>
            </button>
            <!-- Dropdown menu -->
            <ul
              v-if="dropdownOpen"
              class="mt-2 space-y-2 bg-white border border-gray-200 py-2 px-4 rounded-md shadow-lg"
            >
              <li>
                <a @click="navigateTo('projects1')">Frontend</a>
              </li>
              <li>
                <a @click="navigateTo('backend1')">Backend</a>
              </li>
              <li>
                <a @click="navigateTo('fullstack1')">Fullstack</a>
              </li>
            </ul>
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

.myName {
  padding: 20px;
  border-radius:20px;
  background-image: linear-gradient(315deg, rgb(29, 255, 25) 3%, rgba(48, 238, 226, 1) 38%, rgba(60, 132, 206, 1) 68%, rgba(101, 0, 94, 1) 98%); 
  box-shadow: rgba(50, 50, 93, 1) 0px 50px 100px -20px, rgba(0, 0, 0, 0.5) 0px 30px 60px -30px, rgba(10, 37, 64, 0.65) 0px -2px 6px 0px inset;
  font-family: 'Gaegu';
}

.navBut {
  padding: 10px;
  font: 25px;
  color:black;
  border-radius:20px;
  background-image: linear-gradient(315deg, rgb(29, 255, 25) 3%, rgba(48, 238, 226, 1) 38%, rgba(60, 132, 206, 1) 68%, rgba(101, 0, 94, 1) 98%); 
  box-shadow: rgba(50, 50, 93, 1) 0px 50px 100px -20px, rgba(0, 0, 0, 0.5) 0px 30px 60px -30px, rgba(10, 37, 64, 0.65) 0px -2px 6px 0px inset;
  cursor:pointer;
  transform: scale(0.8);
  transition: all .2s ease-out;
  font-family: 'Gaegu';
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


.dropdown-button {
  padding: 10px 20px;
  font-size: 0.8rem;
  font-family: bolder;
  font-family: "Monaco";
  border-radius: 16px;
  background-image: linear-gradient(315deg, rgb(29, 255, 25) 3%, rgba(48, 238, 226, 1) 38%, rgba(60, 132, 206, 1) 68%, rgba(101, 0, 94, 1) 98%); 
  box-shadow: rgba(50, 50, 93, 1) 0px 50px 100px -20px,
    rgba(0, 0, 0, 0.5) 0px 30px 60px -30px, rgba(10, 37, 64, 0.65) 0px -2px 6px 0px inset;
  cursor: pointer;
  transform: scale(0.8);
  transition: all 0.2s ease-in-out;
}

.dropdown-button:hover {
  background-image: linear-gradient(30deg, #f5b6b3, #6272fc);
  font-size: 0.8rem;
  transform: scale(0.9);
  transition-duration: 1s ease-out;
  box-shadow: #030557 0px 25px 35px -5px;
  border-radius: 13px;
  color: #ffffeb;
  border: 0.1px #6e0175;
  animation-play-state: paused;
}

.dropdown-button:hover::after {
  animation-play-state: paused;
}

.dropdown-button + ul {
  width: 100%;
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
  color:black;
  border-radius:16px;
  background-image: linear-gradient(315deg, rgb(29, 255, 25) 3%, rgba(48, 238, 226, 1) 38%, rgba(60, 132, 206, 1) 68%, rgba(101, 0, 94, 1) 98%); 
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
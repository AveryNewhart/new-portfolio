<template>
  <div class="background" ref="background">
    <!-- <div class="wave"></div>
    <div class="wave"></div>
    <div class="wave"></div> -->
  </div>
</template>

<script setup lang="ts">
import { onMounted, onBeforeUnmount, ref } from 'vue';

const backgroundRef = ref<HTMLElement | null>(null);
const currentSection = ref<number>(0);
const targetPosition = ref<number>(0);

const handleScroll = () => {
  // Calculate the section height
  const sectionHeight = window.innerHeight;

  // Calculate the current section (page)
  currentSection.value = Math.floor(window.scrollY / sectionHeight);

  // Calculate the target position for snapping
  targetPosition.value = currentSection.value * sectionHeight;

  // Apply the background position
  if (backgroundRef.value) {
    backgroundRef.value.style.backgroundPositionY = `-${currentSection.value * 100}%`;
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

  <style scoped>
  .background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    z-index: -1;
  }
  
  .wave {
    background: rgba(0, 0, 0, 0.25);
    border-radius: 1000% 1000% 0 0;
    position: absolute;
    width: 200%;
    height: 8em;
    opacity: 0.8;
    bottom: 0;
    left: 0;
  }
  
  .wave:nth-of-type(2) {
    bottom: -1.25em;
    opacity: 0.8;
  }
  
  .wave:nth-of-type(3) {
    bottom: -2.5em;
    opacity: 0.9;
  }
  
  @keyframes wave {
    2% {
      transform: translateX(1);
    }
  
    25% {
      transform: translateX(-25%);
    }
  
    50% {
      transform: translateX(-50%);
    }
  
    75% {
      transform: translateX(-25%);
    }
  
    100% {
      transform: translateX(1);
    }
  }
  
  .background {
    background: linear-gradient(
      315deg,
      rgba(101, 0, 94, 1) 3%,
      rgba(60, 132, 206, 1) 38%,
      rgba(48, 238, 226, 1) 68%,
      rgb(29, 255, 25) 98%
    );
    animation: gradient 15s ease infinite;
    background-size: 400% 400%;
    background-attachment: fixed;
  }
  
  @keyframes gradient {
    0% {
      background-position: 0% 0%;
    }
    50% {
      background-position: 100% 100%;
    }
    100% {
      background-position: 0% 0%;
    }
  }
  </style>
  
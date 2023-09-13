<script setup lang="ts">
</script>

<template>
  <div class="aboutMeDiv">
    <!-- <h1 class="text-center font-bold">About</h1> -->
    <div class="aboutContent">
      <div>
        <div class="whoAmH1">
        <h1>WHO AM I?</h1>
        </div>
        <p class="aboutText">My names Avery Newhart and I am devoted to having a career as a developed after making it my next step once I got out of the United States Air Force. 
          I am eager to learn, grow, and strengthen my skills and everyone else's around me in all ways possible. 
          All I am waiting for is my first opportunity to truly show what I can do in this industry, and I promise you will not be let down.</p>
      </div>
      <img class="myPic" src='/images/myPic.png'>
    </div>
  </div>
</template>

<style scoped>

h1 {
  font-size: 25px;
}

.whoAmH1 {
  margin-bottom: 50px;
}

.aboutMeDiv {
  border: 2px solid red;
  padding: 20px;
  height: 900px;
}

.aboutContent {
  display: flex;
  flex-direction: row;
  align-items: center; 
}

.aboutText {
  flex: 1; 
  padding: 20px;
  background-color: rgba(0, 0, 0, 0.1); 
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect */
  border-radius: 8px;
}

.myPic {
  height: 350px;
  width: 350px;
  margin-left: 20px;
  border-radius: 8px; 
}

@media (max-width: 768px) {
  .aboutContent {
    flex-direction: column;
  }
  .myPic {
    margin-left: 0;
    margin-top: 20px;
  }
}

</style>


<!-- <template>
  <div class="aboutMeDiv">
    <h1>About</h1>
    <p>WHO AM I?</p>
    <p>text about myself is going to go here and will be the left side of the screen, like i have it explained in the commented out code</p>
    <img class="myPic" src='/images/myPic.png'>
    <p>i want the text to be on the left side of the screen on desktop</p>
    <p>i want the image to be on the right side of the screen when on desktop but then when on mobile it will be above the about me section</p>
    <p>i want the image to have cool effects of a cool background to it, make it subtle but stand out.</p>
    <p>for the background of the text have a nice subtle darker type of background with some nice shadow effects/lights to go well with the background of the site.</p>
    <p>look at "ideas" in my discord channel to get a guide of how i want to do it.</p>
  </div>
</template>

<style scoped>

.aboutMeDiv {
  border: 2px solid red;
}

.myPic {
  height: 350px;
  width: 350px;
}

</style> -->
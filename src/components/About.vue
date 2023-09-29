<script setup lang="ts">
</script>

<template>
  <div class="aboutMeDiv">
    <!-- <h1 class="text-center font-bold">About</h1> -->
    <div class="aboutContent">
      <div>
        <div class="whoAmH1">
        <h1 class="text-center">WHO AM I?</h1>
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

@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Black+And+White+Picture&family=Gaegu:wght@700&family=Metal+Mania&family=MuseoModerno:wght@700&family=Prompt:wght@300&family=Rubik+Puddles&family=Zen+Dots&display=swap');

h1 {
  font-size: 25px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect, with no background color, it just makes the h1 pop more since same background color as pages background */
  border-radius: 20px;
}

.whoAmH1 {
  margin-bottom: 50px;
  font-family: 'Black And White Picture';
}

.aboutMeDiv {
  padding: 20px;
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
  height: 500px;
  width: 500px;
  margin-left: 20px;
  border-radius: 8px; 
}

@media (max-width: 768px) {
  .aboutContent {
    flex-direction: column;
  }
  .myPic {
    max-width: 100%;
    height: auto;
    margin-left: 0;
    margin-top: 20px;
  }
}

</style>


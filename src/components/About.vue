<script setup lang="ts">
</script>

<template>
  <div class="aboutMeDiv">
    <div class="aboutContent">
      <div class="mobileDiv">
        <div class="whoAmH1">
        <h1 class="text-center theH1">WHO AM I?</h1>
        </div>
        <p class="aboutText">My name is Avery Newhart, and my journey towards a career in development began as my next step after serving in the United States Air Force.
          I am driven by a deep passion for learning, personal growth, and the collaborative process of elevating everyone's skills in any way possible.
          I am eagerly awaiting that first opportunity to showcase my abilities in this industry, and I am confident that I will exceed your expectations. 
          Together, we can create something remarkable.</p>
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
  padding-left: 150px;
  padding-right: 150px;
  margin-bottom: 75px;
}

.theH1 {
  font-size: 75px;
  white-space: nowrap;
  padding: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect */
  text-decoration: dashed underline white;
}

.aboutMeDiv {
  padding: 20px;
}

.mobileDiv {
  max-width: 100%;
}

.aboutContent {
  display: flex;
  flex-direction: row;
  align-items: center; 
}

.aboutText {
  flex: 1; 
  padding: 20px;
  background-color: rgba(255, 255, 255, 0.3); /* Brighter background with the same translucency */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Shadow effect */
  border-radius: 8px;
  font-family: 'Gaegu';
  font-size: 25px;
  text-align: center;
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
    max-width: 100%;
  }
  .myPic {
    max-width: 100%;
    height: auto;
    margin-left: 0;
    margin-top: 20px;
  }

  .aboutText {
    max-width: 100%;
    font-size: 20px;
    text-align: center;
  }

  .mobileDiv h1 {
    box-shadow: none;
    padding: none;
    display: flex;
    justify-content: center;
  }
}



</style>


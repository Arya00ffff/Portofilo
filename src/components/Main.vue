<script setup>
import LoadingAnimation from './LoadingAnimation.vue'
import Background from './Background.vue'
import LightMode from './LightMode.vue'
import { ref } from 'vue'

const isLightMode = ref(false)

function toggleLightMode() {
  isLightMode.value = !isLightMode.value
  document.body.classList.toggle('light-mode', isLightMode.value)
}
</script>

<template>
  <LoadingAnimation />
  <Background />
  <div class="row-center">
    <div class="left">
      <h3>It's a me! Arya!</h3>
      
    </div>
    <div class="right">
      <LightMode @toggleLightMode="toggleLightMode" />
    </div>
  </div>
  <div class="image-row">
    <img src="@/assets/arya.png" alt="Arya's Avatar" height="480" width="347" class="bunnyPic"/>
    <div class="image-text">
      <h3>I'm Arya! , and I like </h3>
<h1 style="font-size: 70px;">
  Building pixel-perfect<br>
  <span :class="isLightMode ? 'gay-gradient-text' : 'trans-gradient-text'">Interactive</span> apps🌈
</h1>



      <h2>Web-Devloper</h2>
      
    </div>
  </div>
</template>

<style scoped>
.row-center {
  position: absolute;
  left: 0;
  width: 100vw;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.left {
  margin-left: 20vw;
}

.right {
  margin-right: 20vw;
}
.bunnyPic{
  margin-left: 19.5vw;
  margin-top: 10vh;
  border-radius: 5px;
}
.image-row {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.image-text {
  margin-left: 3vw;
  margin-bottom: 0vh;
}
.trans-gradient-text {
  font-size: 70px;
  font-weight: bold;
  background: linear-gradient(to right, #5BCEFA, #F5A9B8, #FFFFFF, #F5A9B8, #5BCEFA);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  display: inline-block;
}
.gay-gradient-text {
  font-weight: bold;
  background: linear-gradient(
    to right,
    #FF0018, /* Red */
    #FFA52C, /* Orange */
    #f5df14, /* Yellow */
    #008018, /* Green */
    #0000F9, /* Blue */
    #86007D  /* Violet */
  );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  display: inline-block;
}
</style>

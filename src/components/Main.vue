<script setup>
import LoadingAnimation from './LoadingAnimation.vue'
import Background from './Background.vue'
import LightMode from './LightMode.vue'
import '@/assets/Main.css'
import { ref } from 'vue'

const isLightMode = ref(false)
const contentVisible = ref(false)

function toggleLightMode() {
  isLightMode.value = !isLightMode.value
  document.body.classList.toggle('light-mode', isLightMode.value)
}

function handleAnimationStart() {
  contentVisible.value = true
}
</script>

<template>
  <LoadingAnimation @animationStart="handleAnimationStart" />
  <Background />
  <div :class="['main-content', { 'content-slide-up': contentVisible }]">
    <div class="row-center">
      <div class="left">
        <h1 style="font-size: 18px; font-weight: bold;">It's a me! Arya!</h1>
      </div>
      <div class="right">
        <LightMode @toggleLightMode="toggleLightMode" />
      </div>
    </div>
    <div class="image-row">
      <img src="@/assets/arya.png" alt="Arya's Avatar" height="480" width="347" class="bunnyPic"/>
      <div class="image-text">
        <h3 style="font-size: 25px; font-weight: 500;position: relative; bottom: -40px;">I'm Arya! , and I like </h3>
        <h1 style="font-size: 70px;">
          Building pixel-perfect<br>
          <span :class="isLightMode ? 'gay-gradient-text' : 'trans-gradient-text'">Interactive</span> apps🌈
        </h1>
        <h2>Web-Developer</h2>
        <br><br>
        <div class="icon-row">

          <a href="https://www.linkedin.com/">
            <i class="fa-brands fa-linkedin linkdin" ></i>  
          </a>
          <a href="http://github.com/arya00ffff/">
          <i class="fa-brands fa-github github"></i>
          </a>
          <a href="mailto:arya@gmail.com">
            <i class="fa-regular fa-envelope email" ></i> 
          </a>
          <i class="fa-brands fa-telegram telegram"></i>
        </div>
      </div>
    </div>
  </div>
<div class="career-container"></div>
</template>


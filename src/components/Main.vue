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

  <Background />
  <div class="row-center">
    <div class="left">
      <h1>Stuff go here</h1>
    </div>
    <div class="right">
      <LightMode @toggleLightMode="toggleLightMode" />
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
</style>
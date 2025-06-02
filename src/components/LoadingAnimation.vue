<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const loading = ref(true)
const preloaderHidden = ref(false)

const hellos = [
  'hello!',
  'hallo!',
  'ciao!',
  'こんにちは！',
  'Привет!',
  '!مرحبا',
  '!سلام'
]

const currentHello = ref(hellos[0])
let index = 0
let intervalId = null

const intervalDuration = 200
const pauseDuration = 500

onMounted(() => {
  setTimeout(() => {
    intervalId = setInterval(() => {
      index++
      if (index < hellos.length) {
        currentHello.value = hellos[index]
      }

      if (index === hellos.length - 1) {
        clearInterval(intervalId)

        setTimeout(() => {
          preloaderHidden.value = true // Start transition

          // After transition ends, remove the preloader
          setTimeout(() => {
            loading.value = false
          }, 600) // match with CSS transition duration
        }, pauseDuration)
      }
    }, intervalDuration)
  }, pauseDuration)
})

onUnmounted(() => {
  clearInterval(intervalId)
})
</script>




<template>
  <div>
    <div
      v-if="loading"
      :class="['preloader', { 'preloader-hidden': preloaderHidden }]"
    >
      <div class="loader-content">
        <h1>{{ currentHello }}</h1>
      </div>
    </div>
  </div>
</template>


<style scoped>

.preloader {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #19191b;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  transition: transform 0.6s ease, opacity 0.6s ease;
}

.preloader-hidden {
  transform: translateY(-100%);
  opacity: 0;
}

.loader-content {
  text-align: center;
  color: #fff;
  font-family: quicksand, cursive;
}

.loader-content h1 {
  font-size: 3rem;
}
</style>

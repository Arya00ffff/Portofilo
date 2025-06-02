<script setup>
import { ref, onMounted } from 'vue'

const container = ref(null)

onMounted(() => {
  const tile = document.createElement('div')
  tile.className = 'tile'
  for (let i = 0; i < 1599; i++) {
    container.value.appendChild(tile.cloneNode())
  }
})
</script>
<template>
    <div id="container" ref="container"></div>
</template>
<style scoped>
#container{
  z-index: -1;
}
</style>
<script setup>

</script>

<template>
  <div id="container"></div>
</template>

<style scoped>
#container {
  width: 120rem;
  aspect-ratio: 1;
  position: absolute;
  top: 0;
  left: 0;
  margin: 0;
  z-index: -1;


  background:
    repeating-linear-gradient(to right, #292737 0 1px, transparent 1px 3rem),
    repeating-linear-gradient(to bottom, #292737 0 1px, transparent 1px 3rem);
}
</style>
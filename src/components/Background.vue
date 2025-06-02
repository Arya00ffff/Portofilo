<template>
  <div id="container"></div>
</template>


<style scoped>
#container {
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  margin: 0;
  z-index: -1;
  overflow: hidden;
  

  background: #19191b;


  -webkit-mask-image:
    repeating-linear-gradient(to right, #000 0 1px, transparent 1px 48px),
    repeating-linear-gradient(to bottom, #000 0 1px, transparent 1px 48px);
  mask-image:
    repeating-linear-gradient(to right, #000 0 1px, transparent 1px 48px),
    repeating-linear-gradient(to bottom, #000 0 1px, transparent 1px 48px);

  background-image: radial-gradient(circle at 50% 50%, #292636 60%, #4b4069 100%);
}
</style>
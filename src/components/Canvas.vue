<template>
  <div class="canvas">
    <Pixel isInCanvas v-for="(color, index) in pixels" :color="color" :key=index :index=index />
  </div>
</template>

<script>
import Pixel from './Pixel';

export default {
  name: 'Canvas',
  components: {
    Pixel
  },
  props: {
    pixels: Array
  }
}
</script>

<style scoped>
.canvas {
  display: flex;
  flex-wrap: wrap;
  margin-left: 50px;
  max-width: 900px;
}
</style>
<template>
  <div class="canvas">
    <Pixel v-for="n in 30*30" :key="n" color='blue'/>
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
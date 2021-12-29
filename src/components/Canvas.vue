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
  }

  @media only screen and (min-width: 320px) {
    .canvas {
      max-width: 300px;
    }
  }

  @media only screen and (min-width: 450px) {
    .canvas {
      max-width: 400px;
    }
  }
  
  @media only screen and (min-width: 576px) {
    .canvas {
      max-width: 560px;
    }
  }

  @media only screen and (min-width: 768px) {
    .canvas {
      max-width: 650px;
    }
  }

  @media only screen and (min-width: 992px) {
    .canvas {
      max-width: 800px;
    }
  }
  
  @media only screen and (min-width: 1200px) {
    .canvas {
      max-width: 1000px;
    }
  }
  
  @media only screen and (min-width: 1400px) {
    .canvas {
      max-width: 1200px;
    }
  }
</style>
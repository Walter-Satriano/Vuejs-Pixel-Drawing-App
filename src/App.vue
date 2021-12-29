<template>
  <div id="app">
    <div class="container">
      <div>
        <Canvas :pixels=pixels />
      </div>
      <div>
        <ColorPicker :color=color />
      </div>
    </div>
  </div>
</template>

<script>
  import Canvas from './components/Canvas'
  import ColorPicker from './components/ColorPicker'

  const defaultColor = 'white'

  export default {
    name: 'App',
    data: function() {
      return {
        color: defaultColor,
        pixels: Array(20 * 20)
          .fill()
          .map( () => defaultColor)
      }
    },
    components: {
      Canvas,
      ColorPicker
    },
    watch: {
      pixels() {
        localStorage.setItem("pixels", JSON.stringify(this.pixels))
      }
    },
    mounted() {
      this.$root.$on('updatecolor', color => {
        this.color = color
      })

      this.$root.$on('clickedpixel', index => {
        this.pixels.splice(index, 1, this.color)
      })

      if(localStorage.getItem("pixels")) {
        this.pixels = JSON.parse(localStorage.getItem("pixels"))
      }
    }
  }
</script>

<style scoped>
  .container {
    background-color: rgb(51, 51, 51);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 40px 0;
  }
</style>

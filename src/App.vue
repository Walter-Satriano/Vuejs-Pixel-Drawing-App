<template>
  <div id="app">
    <ColorPicker :color=color />
    <Canvas :pixels=pixels />
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
      pixels: Array(30 * 30)
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


<style lang="scss">
#app {
  font: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #333;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px 0;
}
</style>

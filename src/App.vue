<template>
  <div id="app">
    <ColorPicker :color=color />
    <Canvas />
  </div>
</template>

<script>
import Canvas from './components/Canvas'
import ColorPicker from './components/ColorPicker'

export default {
  name: 'App',
  data: function() {
    return {
      color: 'white'
    }
  },
  mounted() {
    this.$root.$on('updatecolor', color => {
      this.color = color
    })
  },
  components: {
    Canvas,
    ColorPicker
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

<template>
  <div>
    <div>
      <h3>Select a Color:</h3>
    </div>
    <div class="color-picker-container">
      <Pixel isInColorPicker color='white' :current="color == 'white' ? true : false" />
      <Pixel isInColorPicker color='silver' :current="color == 'silver' ? true : false" />
      <Pixel isInColorPicker color='gray' :current="color == 'gray' ? true : false" />
      <Pixel isInColorPicker color='black' :current="color == 'black' ? true : false" />
      <Pixel isInColorPicker color='cyan' :current="color == 'cyan' ? true : false" />
      <Pixel isInColorPicker color='aquamarine' :current="color == 'aquamarine' ? true : false" />
      <Pixel isInColorPicker color='lightblue' :current="color == 'lightblue' ? true : false" />
      <Pixel isInColorPicker color='blue' :current="color == 'blue' ? true : false" />
      <Pixel isInColorPicker color='darkblue' :current="color == 'darkblue' ? true : false" />
      <Pixel isInColorPicker color='purple' :current="color == 'purple' ? true : false" />
      <Pixel isInColorPicker color='magenta' :current="color == 'magenta' ? true : false" />
      <Pixel isInColorPicker color='pink' :current="color == 'pink' ? true : false" />
      <Pixel isInColorPicker color='yellow' :current="color == 'yellow' ? true : false" />
      <Pixel isInColorPicker color='orange' :current="color == 'orange' ? true : false" />
      <Pixel isInColorPicker color='red' :current="color == 'red' ? true : false" />
      <Pixel isInColorPicker color='brown' :current="color == 'brown' ? true : false" />
      <Pixel isInColorPicker color='maroon' :current="color == 'maroon' ? true : false" />
      <Pixel isInColorPicker color='lime' :current="color == 'lime' ? true : false" />
      <Pixel isInColorPicker color='green' :current="color == 'green' ? true : false" />
      <Pixel isInColorPicker color='olive' :current="color == 'olive' ? true : false" />
    </div>
  </div>
</template>

<script>
  import Pixel from './Pixel'

  export default {
    name: 'ColorPicker',
    props: {
      color: String
    },
    components: {
      Pixel
    }
  }
</script>

<style scoped>
  h3 {
    color: white;
    text-align: center;
    margin-top: 30px;
    text-transform: uppercase;
  }

  .color-picker-container {
    display: flex;
    flex-wrap: wrap;
    margin-top: 5px;
  }

  @media only screen and (min-width: 320px) {
    h3 {
      font-size: 0.9rem;
    }
  }

  @media only screen and (min-width: 576px) {
    h3 {
      font-size: 1.1rem;
    }
  }

  @media only screen and (min-width: 768px) {
    h3 {
      font-size: 1.3rem;
    }
  }

  @media only screen and (min-width: 768px) {
    h3 {
      font-size: 1.5rem;
    }
  }
  
  @media only screen and (min-width: 1200px) {
    h3 {
      font-size: 1.8rem;
    }
  }

  @media only screen and (min-width: 1400px) {
    h3 {
      font-size: 2rem;
    }
  }  
</style>
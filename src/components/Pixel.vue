<template>
  <div @click="handleClick" :class="['pixel', color, current ? 'current' : '']"></div>
</template>

<script>
  export default {
    name: 'Pixel',
    props: {
      color: String,
      current: Boolean,
      isInColorPicker: Boolean,
      isInCanvas: Boolean,
      index: Number
    },
    methods: {
      handleClick: function() {
        if (this.isInColorPicker) {
          this.$root.$emit('updatecolor', this.color)
        }
        if (this.isInCanvas) {
          this.$root.$emit('clickedpixel', this.index)
        }
      }
    }
  }
</script>

<style scoped>
  @import "../assets/listcolor.css";

  .pixel {
    border: 1px solid lightgrey;
    width: 30px;
    height: 30px;
    box-sizing: border-box;
  }

  .pixel.current {
    border: 4px solid #E55451;
  }

  @media only screen and (min-width: 320px) {
    .pixel {
      width: 15px;
      height: 15px;
    }

    .pixel.current {
      border: 2px solid #E55451;
    }
  }

  @media only screen and (min-width: 450px) {
    .pixel {
      width: 20px;
      height: 20px;
    }
  }

  @media only screen and (min-width: 576px) {
    .pixel {
      width: 28px;
      height: 28px;
    }
  }

  @media only screen and (min-width: 768px) {
    .pixel {
      width: 32.5px;
      height: 32.5px;
    }
  }

  @media only screen and (min-width: 992px) {
    .pixel {
      width: 40px;
      height: 40px;
    }
    
    .pixel.current {
      border: 3px solid #E55451;
    }
  }

  @media only screen and (min-width: 1200px) {
    .pixel {
      width: 50px;
      height: 50px;
    }
    
    .pixel.current {
      border: 4px solid #E55451;
    }
  }
  
  @media only screen and (min-width: 1400px) {
    .pixel {
      width: 60px;
      height: 60px;
    }
  }   
</style>
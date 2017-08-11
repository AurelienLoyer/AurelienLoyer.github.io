<template>
    <canvas @click="handleResize"></canvas>
</template>

<script>

export default {
  
  name: 'stars',

  data () {
    return {
      'STAR_COLOURS': ['#ffffff'],
      'HEIGHT': window.innerHeight, 
      'WIDTH': window.innerWidth,
    }
  },

  mounted(){
    this.init()
  },

  created: function () {
    window.addEventListener('resize', this.handleResize)
  },
  beforeDestroy: function () {
    window.removeEventListener('resize', this.handleResize)
  },

  methods: {

    handleResize () {
      console.log('resize')
      this.init()
    },

    random (min, max) {
      return Math.round((Math.random() * max - min) + min);
    },

    star_field (context, star_number) {
      
      let x // x position of the star
      let y // y position of the star
      let brightness // brightness of the star
      let radius // radius of the star

      // draw the black night sky
      context.fillStyle = '#000'
      context.fillRect(0, 0, this.WIDTH, this.HEIGHT)
      
      // save the previous canvas context state
      context.save()
      
      for (var i = 0; i < star_number; i++) {

        x = Math.random() * this.WIDTH // random x position
        y = Math.random() * this.HEIGHT // random y position
        radius = Math.random() * 3.5 // random radius
        brightness = this.random(80, 100) / 100

        // start drawing the star
        context.beginPath()
        // set the brightness of the star
        context.globalAlpha = brightness
        // choose a random star colour
        context.fillStyle = this.STAR_COLOURS[this.random(0, this.STAR_COLOURS.length)]
        // draw the star (an arc of radius 2 * pi)
        context.arc(x, y, radius, 0, Math.PI * 2, true)
        // fill the star and stop drawing it
        context.fill()
        context.closePath()
      }
      
      // restore the previous context state
      context.restore()
    },

    init () {
      // find the canvas and create its context
      const canvas = document.getElementsByTagName('canvas')[0]
      const context = canvas.getContext('2d')
      
      // set up the width and height
      canvas.width = this.WIDTH
      canvas.height = this.HEIGHT
      
      // create a star field
      this.star_field(context, 100)
      
      // create a new star field when you click on the canvas
      canvas.addEventListener ('click', function () {
        this.star_field(context, 100)
      }, false)
    }
  },
}
</script>

<style scoped lang="scss">
  canvas{
    height: 100%;
    position: absolute;
    width: 100%;
    z-index: -1;
  }


</style>

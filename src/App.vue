<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Carousel from './components/carousel/Carousel.vue'
export default {
  data: () => ({
    slides: [
      'https://image.shutterstock.com/shutterstock/photos/2068574411/display_1500/stock-photo-elderly-man-walking-with-walking-cane-in-hand-behind-his-back-old-man-with-cane-enjoying-walk-in-2068574411.jpg',
      'https://picsum.photos/900/400',
      'https://image.shutterstock.com/shutterstock/photos/2068574411/display_1500/stock-photo-elderly-man-walking-with-walking-cane-in-hand-behind-his-back-old-man-with-cane-enjoying-walk-in-2068574411.jpg',
      'https://picsum.photos/900/400',
      'https://image.shutterstock.com/shutterstock/photos/2068574411/display_1500/stock-photo-elderly-man-walking-with-walking-cane-in-hand-behind-his-back-old-man-with-cane-enjoying-walk-in-2068574411.jpg',
      'https://picsum.photos/900/400',
    ]
  }),
  components: {Carousel}
}
</script>

<template>
  <carousel 
  :slides="slides" 
  controls 
  indicators
  :interval="3000"
  width="400"
  height="200"
  ></carousel>
</template>

<style scoped>

</style>

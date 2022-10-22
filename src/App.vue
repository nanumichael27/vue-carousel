<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Carousel from './components/carousel/Carousel.vue'
export default {
  data: () => ({
    slides: [
      'https://image-placeholder.com/images/actual-size/600x400.png',
      'https://image-placeholder.com/images/actual-size/600x400.png',
      'https://image-placeholder.com/images/actual-size/600x400.png',
      'https://image-placeholder.com/images/actual-size/600x400.png',
      'https://image-placeholder.com/images/actual-size/600x400.png',
    ]
  }),
  components: {Carousel}
}
</script>

<template>
  <carousel :slides="slides" ></carousel>e
</template>

<style scoped>

</style>

<script>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
export default {
  data: () => ({
    slides: [
      'https://picsum.photos/id/1032/900/400',
      'https://picsum.photos/id/1033/900/400',
      'https://picsum.photos/id/1035/900/400',
      'https://picsum.photos/id/1036/900/400',
      'https://picsum.photos/id/1037/900/400',
    ]
  })
}
</script>

<template>
  <div class="carousel">
    <div class="carousel-inner">
      <div class="carousel-item" v-for="slide in slides">
        <img :src="slide" alt="">
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>

<template>
    <div class="carousel">
        <div class="carousel-inner">
            <caruosel-item v-for="(slide, index) in slides" 
            :slide="slide" 
            :key="`slide-${index}`"></caruosel-item>
        </div>
  </div>
</template>

<script>
    import CaruoselItem from './CarouselItem.vue'

    export default {
        props: ['slides'],
        components: { CaruoselItem }
    }
</script>
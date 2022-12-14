<template>
    <div class="carousel">
        <div class="carousel-inner" :style="dimension">
            <carousel-indicators
            v-if="indicators"
            :count="slides.length"
            :active="currentSlide"
            @switch="switchSlide($event)"></carousel-indicators>
            <caruosel-item v-for="(slide, index) in slides" 
            :slide="slide" 
            :key="`slide-${index}`"
            :current-slide="currentSlide"
            :index="index"
            :direction="direction"
            @mouseenter="stopSlideTimer"
            @mouseout="startSlideTimer"></caruosel-item>
            <carousel-controls
            v-if="controls"
            @prev="prev" @next="next"></carousel-controls>
        </div>
  </div>
</template>

<script>
    import CaruoselItem from './CarouselItem.vue'
    import CarouselControls from './CarouselControls.vue'
    import CarouselIndicators from './CarouselIndecators.vue'

    export default {
        props: {
            slides:{
                type: Array,
                required: true
            },
            controls:{
                type: Boolean,
                default: false,
            },
            indicators:{
                type: Boolean,
                default: false,
            },
            interval:{
                type: Number,
                default: 5000
            },
            width:{
                type: Number,
                default: 900,
            },
            height:{
                type: Number,
                default: 400,
            },
        },
        computed:{
            dimension (){
                return{
                    width: this.width + 'px',
                    height: this.height + 'px',
                }
            }
        },
        components: { CaruoselItem, CarouselControls, CarouselIndicators },
        data: () => ({
            currentSlide: 0,
            slideInterval: null,
            direction: 'right',
        }),
        mounted () {
            this.startSlideTimer();
        },
        methods: {
            setCurrentSlide(index) {
                this.currentSlide = index;
            },
            prev(step  = -1){
                const index = this.currentSlide > 0
                ? this.currentSlide + step: this.slides.length - 1;
                this.setCurrentSlide(index);
                this.direction = 'left'
                this.startSlideTimer()
            },
            _next(step = 1){
                const index = this.currentSlide < this.slides.length -1
                ? this.currentSlide + step: 0;
                this.setCurrentSlide(index);
                this.direction = 'right'
            },
            next(step = 1){
                this._next(step)
                this.startSlideTimer()
            },
            startSlideTimer(){
                this.stopSlideTimer()
                this.slideInterval = setInterval(() => {
                this._next()
                }, this.interval)
            },
            stopSlideTimer(){
                clearInterval(this.slideInterval);
            },
            switchSlide(index){
                // index - currentSlide
                const step = index - this.currentSlide;
                if(step > 0){
                    this.next(step);
                }else{
                    this.prev(step);
                }
            }
        },
        beforeUnmount() {
            this.stopSlideTimer()
        }
    }
</script>

<style scoped>
.carousel{
    display: flex;
    justify-content: center;
}

.carousel-inner{
    position: relative;
    overflow:hidden;
}
</style>
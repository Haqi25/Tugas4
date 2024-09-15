<template>
  <div class="app">
    <carousel 
       @next="next"
       @prev="prev"
    >
      <carousel-slide v-for="(slide, index) in slides" 
      :key="slide" 
      :index="index"
      :visibleSlide="visibleSlide"
      :direction="direction"
      >
      
        <img :src="slide" />
    
        
      </carousel-slide>
    </carousel>
    <div id="appp">
    <!-- Menggunakan komponen CounterButton -->
    <CounterButton />
  </div>
  <div>
    <div id="ivu">
    <BoxColor />
  </div>
  </div>
</div>
</template>

<script>
import Carousel from './components/Carousel.vue';
import CarouselSlide from './components/CarouselSlide.vue'; 
import CounterButton from './components/counterbutton.vue';
import BoxColor from './components/BoxColor.vue'
export default {
  data() {
    return {
      slides: [
        'https://picsum.photos/id/240/600/350',
        'https://picsum.photos/id/220/600/350',
        'https://picsum.photos/id/230/600/350',
        'https://picsum.photos/id/261/600/350',
        'https://picsum.photos/id/250/600/350',
      ],
      visibleSlide: 0,
      direction: '',
    }
  },
  computed: {
      slidesLen() {
        return this.slides.length;
      }
  },
  methods : {
        next(){
            if(this.visibleSlide >= this.slidesLen - 1) {
             this.visibleSlide = 0;
        }else{
           this.visibleSlide++;
      }
           this.direction = "left"
        },
        prev(){
          if(this.visibleSlide <= 0) {
            this.visibleSlide = this.slidesLen - 1;
          }else {
            this.visibleSlide--;
          }
            this.direction = "right"
        }
  },
  components: {
    Carousel,
    CarouselSlide,
    CounterButton,
    BoxColor,
  }
}


</script>

<style>

</style>

<template>
    
    <div class="container">
     
      <span 
        v-for="(color, index) in colors" 
        :key="index" 
        :style="{ backgroundColor: color }" 
        class="color" 
        @click="changeBackground(color)">
      </span>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
       
        colors: ['#00008B', '#7FFFD4', '#008B8B', '#66CDAA', '#C71585', '#FFFFFF','#000000','#696969',
        '#F0FFFF', '#E6E6FA'],
      }
    },
    methods: {
    
      changeBackground(color) {
        document.body.style.backgroundColor = color;
      }
    }
  }
  </script>
  
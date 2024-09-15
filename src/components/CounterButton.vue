<template>
    <div class="counter">
      <!-- Angka count berada di atas tombol reset -->
      
  
      <div class="button-container">
        <div class="button-wrapper">
        <div class="count-display">{{ count }}</div>
        <button @click="count++" class="btn btn-green1">+</button>
        <button @click="resetCount" class="btn btn-reset">Reset</button>
        <button @click="count--" class="btn btn-red2">-</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "CounterButton",
    data() {
      return {
        count: 0,  // Menginisialisasi count dengan nilai awal 0
      };
    },
    methods: {
      resetCount() {
        this.count = 0;  // Fungsi untuk mereset nilai count menjadi 0
      }
    }
  };
  </script>
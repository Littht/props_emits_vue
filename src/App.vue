<script setup>
import { ref } from 'vue';
import SizeSelector from './components/SizeSelector.vue';

const selectedSize= ref("")
</script>

<template> 
<div class="main">
  <h1>seleccione una talla: {{selectedSize}}</h1>  
  <div>
    <SizeSelector
      :selectedSize="selectedSize"
      @on-change-size="selectedSize = $event"
    />
  </div>
</div>
</template>

<style>
  .main{
    flex-direction: column;
  }

  .active{
    background-color: #363636 !important;
    color: white;
    transition: all .3s ease-out;
  }
</style>

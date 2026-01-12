<script setup>
import {ref} from 'vue';
import sockImage from './assets/images/boot2.jpg';
const product = ref('Socwerks');
const image = ref(sockImage);
// const inStock = false;
const inventory = ref(-5);
</script>
<template>
  <div class="nav-bar"></div>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <img width="100px"  v-bind:src="image" alt="">
      </div>
      <div class="product-info">
        <h1>{{ product}}</h1>
        <p  v-if="inventory > 10">In Stock</p>
        <p v-else-if="inventory <= 10 && inventory > 0">Almost Sold Out!</p>
        <p v-else>Out of Stock</p>
      </div>
    </div>
  </div>

 </template>

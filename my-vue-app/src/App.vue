<script setup>
  import {ref, computed} from 'vue'
  import ProductDisplay from '@/components/ProductDisplay.vue';
const cart = ref(0)
const premium = ref(true)
const updateCart = () => {
  cart.value += 1
}
</script>

<template>
  <div>
  <div class="nav-bar"></div>
  <div class="cart">Cart ({{ cart }})</div>
   <ProductDisplay :premium12="premium" @add-to-cart="updateCart"></ProductDisplay> 
</div>

 </template>

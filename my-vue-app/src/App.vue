<script setup>
import {computed, ref} from 'vue';
import stockImage from './assets/images/boot1.jpg';
import stockImage1 from './assets/images/boot2.jpg';

const product = ref('Socwerks');
const image = ref(stockImage);
const details = ref(["Cotton","Red","M"])
const inStock = false;
const inventory = ref(100);
const cart = ref(100);
const proudct = ref("Socwerks")
const brand = ref("Nike")
const title = computed(() => {
  return product.value + brand.value
})
const addToCart = () => cart.value += 1;
const updateImage = (variant) => image.value = variant
const variants = ref([ {id: 12, color: "Green",image: stockImage}, {id: 13, color: "Blue",image: stockImage1}]);
</script>
<template>
  <div class="nav-bar"></div>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <img width="100px"  v-bind:src="image" alt="">
      </div>
      <div class="product-info">
        <h1>{{ title}}</h1>
        <p  v-if="inventory > 10">In Stock</p>
        <p v-else-if="inventory <= 10 && inventory > 0">Almost Sold Out!</p>
        <p v-else>Out of Stock</p>
        <ul>
          <li v-for="detail in details" :key="detail.id">{{ detail }}</li>
        </ul>

        <div class="color-circle" :style="{ backgroundColor: variant.color }" v-for="variant in variants" :key="variant.id" @mouseover="updateImage(variant.image)"></div>
        <button :class="{ disabledButton: !inStock}" :disabled="!inStock" v-on:click="addToCart">Add to cart</button>
      </div>
      <div>Cart ({{cart }})</div>
    </div>
  </div>

 </template>

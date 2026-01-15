<script setup>
import {computed, ref} from 'vue';
import stockImage from '@/assets/images/boot1.jpg';
import stockImage1 from '@/assets/images/boot2.jpg';

const props = defineProps({  
    premium: {
        type: Boolean,
        required: true
    }   
})

const product = ref("Socwerks")
const brand = ref("Nike")

const selectVariant = ref(0)

const details = ref(["Cotton","Red","M"])

const variants = ref([ 
  {id: 12, color: "Green",image: stockImage, quantity: 50},
  {id: 13, color: "Blue",image: stockImage1, quantity: 0}
]);



const title = computed(() => {
  return product.value + '' + brand.value
})

const addToCart = () => cart.value += 1;
const updateVariant = (index) => {
  selectVariant.value = index
}

const image = computed(() => {
  return variants.value[selectVariant.value].image
})

const inStock  = computed(() => {
  return variants.value[selectVariant.value].quantity > 0
})

const shipping = computed(() => {
    if (props.premium){
        return 'Free'
    }else{
        return 2.99
    }
})

</script>

<template>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <img width="100px"  v-bind:src="image" alt="">
      </div>
      <div class="product-info">
        <h1>{{ title}}</h1>
        <p  v-if="inStock">In Stock</p>
        <p v-else>Out of Stock</p>
        <p>Shipping</p>
        <ul>
          <li v-for="detail in details" :key="detail.id">{{ detail }}</li>
        </ul>

        <div 
        v-for="(variant, index) in variants"
        :key="variant.key" 
         @mouseover="updateVariant(index)"
         class="color-circle"
        :style="{ backgroundColor: variant.color }" 
        ></div>

        
        <button class="button" 
        :class="{ disabledButton: !inStock}" 
        :disabled="!inStock" 
        v-on:click="addToCart">Add to cart</button>
      </div>
      <!-- <div>Cart ({{cart }})</div> -->
    </div>
  </div>  
</template>
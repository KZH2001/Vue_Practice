<script setup>
import {computed, ref} from 'vue';
import stockImage from '@/assets/images/boot1.jpg';
import stockImage1 from '@/assets/images/boot2.jpg';
import ReviewForm from './ReviewForm.vue';
import ReviewList from './ReviewList.vue'

const props = defineProps({  
    premium12: {
        type: Boolean,
        required: false
    }   
})

const reviews = ref([])

const emit = defineEmits(['add-to-cart'])
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

const addToCart = () => {
    emit('add-to-cart')
}



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
    if (props.premium12){
        return 'Free'
    }else{
        return 2.99
    }
})

const addReview = (review) => {
  reviews.value.push(review)
}

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
        <p>Shipping : {{ shipping }}</p>
        <ul>
          <li v-for="detail in details" :key="detail">{{ detail }}</li>
        </ul>

        <div 
        v-for="(variant, index) in variants"
        :key="variant.id" 
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
    <ReviewList :reviews="review"></ReviewList>
    <ReviewForm @review-submitted="addReview"></ReviewForm>
  </div>  
</template>
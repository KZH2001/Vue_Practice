<script setup>
    import {reactive} from 'vue'

    const emit = defineEmits(['review-submitted'])
    const review = reactive ({
        name: '',
        content: '',
        rating: null
    })

    const onSubmit = () => {
        const productReview = {
            name: review.name,
            content: review.content,
            rating: review.rating
        }
        emit('review-submitted', productReview)

        review.name = ''
        review.content = ''
        review.rating = null
    }
</script>

<template>
    
    <form class="review-form" @submit.prevent="onSubmit">
        <h3>Leave a review</h3>
        <label for="name">Name: </label>
        <input v-model="review.name" id="name" type="text">

        <label for="review">Review: </label>
        <textarea v-model="review.content" name="" id="review" cols="30" rows="10"></textarea>

        <label for="rating">Rating: </label>
        <select name="" id="rating" v-model.number="review.rating">
            <option value="">5</option>
            <option value="">4</option>
            <option value="">3</option>
            <option value="">2</option>
            <option value="">1</option>
        </select>

        <input class="button" type="submit" value="Submit">
    </form>
</template>
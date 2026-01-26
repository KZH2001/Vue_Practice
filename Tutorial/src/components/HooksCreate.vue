<template>
    <div>
        <form @submit.prevent="createPost">
            <label for="">Enter Title</label>
            <input type="text" v-model="formData.title">
            <button>Create</button>
        </form>
    </div>
</template>

<script>
import axios from 'axios';

    export default {
        data(){
            return{
                formData: {
                    title: ''
                }
            }
        },
        methods: {
            createPost() {
                axios
                .post('https://jsonplaceholder.typicode.com/posts', this.formData)
                .then((response) => {
                    console.log(response)})
                .catch((error) => {
                    console.log(error)
                })
 
            }
        }
    }
</script>

<style scoped>

</style>
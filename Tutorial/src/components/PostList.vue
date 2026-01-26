<template>
    <div>
        <button @click="getPosts">Post</button>
        <div v-for="post in posts" :key="post.id">
            <h5> {{ post.title }}</h5>
        </div>
    </div>
</template>

<script>
import axios  from 'axios';
    export default {
        data() {
            return{
                posts: [],
            }
        },
        methods: {
            getPosts(){
                axios
                .get("https://jsonplaceholder.typicode.com/posts")
                .then((response) => {
                    console.log(response.data) 
                    this.posts = response.data 
                })
                .catch((error) => {
                    console.log(error);
                })
            }
        }
    }
</script>

<style scoped>

</style>
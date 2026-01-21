<style></style>


<template>
    <h3>  {{ name }}</h3>
</template>


<script>
    export default{
        props: {
        name: String,
        likes: Number,
    }
}
</script>
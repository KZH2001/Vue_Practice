<style></style>


<template>
  <div>
      <h3>  {{ name }}</h3>
    <h2 v-bind="$attrs">  {{ title }}</h2>
    <h3>{{ likes }}</h3>
</div>
</template>


<script>
    export default{
        props: {
            title:{
                type: String,
                required: true,
                default: "Test"
            },
        name: String,
        likes: Number,
    },
    inheritAttrs: false,
}
</script>
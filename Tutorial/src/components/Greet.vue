<style>

</style>

<template>
<h1>{{ number }}</h1>
<button @click="number = number + 1">Click</button>
<h2>Hello {{ name }} aka {{ heroName }}, {{ age }}</h2>
</template>


<script>
    export default{

        name: "Greet",
        props: ['name','heroName','age'],  

      data(){
        return{
              number: 0,
        }
      }
    }
</script>
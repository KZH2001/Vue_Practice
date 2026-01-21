<style>

</style>

<template>
<h1>{{ number }}</h1>
<button @click="number = number + 1">Click</button>
</template>


<script>
    export default{

      data(){
        return{
              number: 0,
        }
      }
    }
</script>
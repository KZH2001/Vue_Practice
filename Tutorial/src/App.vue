

<template>
<h3>The total reusult is {{ add(2,3,4) }}</h3>

<h3>{{ name }}</h3>
<button  v-on:click="name = 'Batman'">Change name</button>
</template>

<style scoped>

</style>

<script >
  export default{

    
    data(){
      return{
        name: 'Superman'
      }
    },
     methods: {
    add(a,b,c){
      return a+b+c
    },

  }

}
 
</script>



  <template>
  <h3>The total reusult is {{ add(2,3,4) }}</h3>
  <h3>{{ number  }}</h3>

  <h3>{{ name }}</h3>
  <button  v-bind:style="{color:color}" v-on:click="name = 'Batman'">Change name</button>
  <button @click="increaseNumber(1)">Increase 1</button>
  <button @click="increaseNumber(5)">Increase 5</button>
  <button @click="decreasNumber(1)">Decrease 1</button>
  <button @click="decreasNumber(5)">Decrease 5</button>

  </template>

  <style scoped>

  </style>

  <script >
    export default{

      
      data(){
        return{
          name: 'Superman',
          color: 'red',
          number: 0
        }
      },
      methods: {
      add(a,b,c){
        return a+b+c
      },

      increaseNumber(num){
        this.number += num
      },

      decreaseNumber(num){
        this.number -= num
      }

    }

  }
  
  </script>

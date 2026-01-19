

  <template>
  <h3>The total reusult is {{ add(2,3,4) }}</h3>
  <h3>{{ number  }}</h3>

  <h3>{{ name }}</h3>
  <button  v-bind:style="{color:color}" v-on:click="name = 'Batman'">Change name</button>
  <button @click="increaseNumber(1)">Increase 1</button>
  <button @click="increaseNumber(5)">Increase 5</button>
  <button @click="decreaseNumber(1)">Decrease 1</button>
  <button @click="decreaseNumber(5)">Decrease 5</button>

  <pre>{{ JSON.stringify(formValues, null, 2) }}</pre>


  <form action="">
    <label for="name">Name</label>
    <input v-model="formValues.name" id="name" type="text">
    <br>

    <select name="" id="" v-model="formValues.role">
      <option value="">Select Role</option>
      <option value="Web">Web</option>
      <option value="Network">Network</option>
    </select>
    <br>

    <label for="">Remote</label>
    <input v-model="formValues.remote" type="checkbox" true-value ="Yes" false-value="No">
    
  </form>
  </template>

  <style scoped>

  </style>

  <script >
    export default{

      
      data(){
        return{
          name: 'Superman',
          color: 'red',
          number: 0,
          formValues: {
            name: '',
            role: '',
            remote: "No",
            skill: [],
          }
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

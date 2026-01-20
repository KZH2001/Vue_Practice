

  <template>
  <h3>The total reusult is {{ add(2,3,4) }}</h3>
  <h3>{{ number  }}</h3>

  <h3 v-once>{{ name }}</h3>
  <button  v-bind:style="{color:color}" v-on:click="name = 'Batman'">Change name</button>
  <button @click="increaseNumber(1)">Increase 1</button>
  <button @click="increaseNumber(5)">Increase 5</button>
  <button @click="decreaseNumber(1)">Decrease 1</button>
  <button @click="decreaseNumber(5)">Decrease 5</button>

  <pre>{{ JSON.stringify(formValues, null, 2) }}</pre>


  <form action="" @submit="submitForm">
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
    <br>
    <label for="">HTML</label>
    <input v-model="formValues.skill" value="HTML" type="checkbox">

     <label for="">CSS</label>
    <input v-model="formValues.skill" value="CSS" type="checkbox">

    <button>Submit</button>
  </form>


  <di>Total - {{ items.reduce((total,curr)=> (total =  total + curr.price),0) }}</di>
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
          },
            items: [
              {
              id: 1,  
              firstName: "Kyz",
              price: 300
              },
               {
              id: 2,  
              firstName: "Rye",
              price: 1300
              },
               {
              id: 3,  
              firstName: "Crt",
              price: 2100
              },
               {
              id: 4,  
              firstName: "Cxz",
              price: 3120
              },
               {
              id: 5,  
              firstName: "Yte",
              price: 3200
              },
            ]
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
      },

      submitForm(w){
        w.preventDefault();
        console.log("result", this.formValues)
      }

    }

  }
  
  </script>

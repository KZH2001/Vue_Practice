<template>

  <!-- Popup -->
  <button @click="showPopup = true">Show</button>
  <Popup v-show="showPopup" @close="closePopup"></Popup>
  <!-- Popup -->

  <hr>
  <h3>The total result is {{ add(2, 3, 4) }}</h3>
  <h3>{{ number }}</h3>

  <h3 v-once>{{ name }}</h3>
  <button v-bind:style="{ color: color }" v-on:click="name = 'Batman'">
    Change name
  </button>
  <button @click="increaseNumber(1)">Increase 1</button>
  <button @click="increaseNumber(5)">Increase 5</button>
  <button @click="decreaseNumber(1)">Decrease 1</button>
  <button @click="decreaseNumber(5)">Decrease 5</button>

  <h4>Volume - {{ volume }}</h4>
  <button @click="volume += 1">Increase Volume</button>
  <button @click="volume -= 1">Decrease Volume</button>

  <pre>{{ JSON.stringify(formValues, null, 2) }}</pre>

  <form action="" @submit="submitForm">
    <label for="name">Name</label>
    <input v-model="formValues.name" id="name" type="text" />
    <br />

    <select name="" id="" v-model="formValues.role">
      <option value="">Select Role</option>
      <option value="Web">Web</option>
      <option value="Network">Network</option>
    </select>
    <br />

    <label for="">Remote</label>
    <input
      v-model="formValues.remote"
      type="checkbox"
      true-value="Yes"
      false-value="No"
    />
    <br />
    <label for="">HTML</label>
    <input v-model="formValues.skill" value="HTML" type="checkbox" />

    <label for="">CSS</label>
    <input v-model="formValues.skill" value="CSS" type="checkbox" />

    <button>Submit</button>
  </form>

  <!-- <di>Total - {{ items.reduce((total,curr)=> (total =  total + curr.price),0) }}</di> -->
  <div>
    Total - {{ items.reduce((total, curr) => (total += curr.price), 0) }}
  </div>

  <label for="">Name</label>
  <input id="art" v-model="person.name" type="text" />
  <br />
  <label for="">Email</label>
  <input v-model="person.email" type="email" />

  <Greet name="Bruce" heroName="Mike" age="32"></Greet>
  <Greet name="Clark" heroName="John"></Greet>
  <Greet name="Diana" heroName="Son"></Greet>
  <Greet></Greet>
  <hr />
  <!-- <h3>{{ title }}</h3> -->

  <Article
    id="my-article-test"
    title="This is Article"
    name="Lynx"
    :likes="23"
  ></Article>
  <hr>

  <ComponentC></ComponentC>
  <hr>

<!-- Card  Slot-->
  <!-- <Card content="Card content 1"></Card>
  <Card content="Card content 2 12"></Card> -->
  <Card>
    <h2>Hello this is slot</h2>
  </Card>

  <Card>
    <h3>Hello </h3>
  </Card>
<hr>
 
 <!-- Card slot with name -->
  <Card>
  
      <template v-slot:header>
        <h3>This is header</h3>
      </template>

      <template v-slot:content>
        <h3>This is content</h3>
      </template>

      <template v-slot:footer>
        <h4>This is footer</h4>
      </template>

  </Card>

  <hr>

  <NameList>
    <template v-slot:default="slotProps">

      <h3>{{ slotProps.firstName09 }}</h3>
    </template>
  </NameList>

  <hr>
<h4>App Component Text</h4>
  <ChildStyles></ChildStyles>
  <hr>

  <!-- Dynamic Component, Menu  -->
  <button @click="isTab = 'TabA'">Tab A</button>
  <button @click="isTab = 'TabB'">Tab B</button>
  <button @click="isTab = 'TabC'">Tab C</button>

<keep-alive>
<component :is="isTab"></component>
</keep-alive>
</template>





<style scoped>
h4{
  color:red;
}
</style>

<script>
import Card from "./components/Card.vue";
import Greet from "./components/Greet.vue";
import Article from "./components/Article.vue";
import ComponentC from "./components/ComponentC.vue";
import Popup  from "./components/Popup.vue";
import NameList from "./components/NameList.vue";
import ChildStyles from "./components/ChildStyles.vue";
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";
export default {
  components: {
    Greet,
    Article,
    ComponentC,
    Popup,
    Card,
    NameList,
    ChildStyles,
    TabA,
    TabB,
    TabC,
  },

  data() {
    return {
      isTab: 'TabA',
      name: "Superman",
      color: "red",
      number: 0,
      showPopup: false,
      formValues: {
        name: "",
        role: "",
        remote: "No",
        skill: [],
      },
      items: [
        {
          id: 1,
          firstName: "Kyz",
          price: 300,
        },
        {
          id: 2,
          firstName: "Rye",
          price: 1300,
        },
        {
          id: 3,
          firstName: "Crt",
          price: 21030,
        },
        {
          id: 4,
          firstName: "Cxz",
          price: 3120,
        },
        {
          id: 5,
          firstName: "Yte",
          price: 3200,
        },
      ],
      person: {
        name: "Kyx",
        email: "kyaw@gmail.com",
      },
      volume: 0,
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },

     closePopup(name){
        this.showPopup = false
        console.log('name',name)
      },


    increaseNumber(num) {
      this.number += num;
    },

    decreaseNumber(num) {
      this.number -= num;
    },

    submitForm(w) {
      w.preventDefault();
      console.log("result", this.formValues);
    },
  },
  watch: {
    volume(value) {
      if (value == 3) {
        alert("Alert");
      }
    },

    person: {
      handler(newValue) {
        console.log(`Hello ${newValue.name} and ${newValue.email}`);
      },
      deep: true,
    },
  },
  provide: {
    name: "Lynx"
  }
};
</script>

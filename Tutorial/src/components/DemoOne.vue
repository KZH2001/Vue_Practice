<template>
  <div>
    <h3>{{ firstName }} {{ lastName }}</h3>
    <button @click="increaseNumber">Count: {{ count }}</button>
    <button @click="changeHero">Change Hero</button>
  </div>
</template>

<script>
import { reactive, toRefs, ref } from 'vue'

export default {
  setup() {
    const state = reactive({
      firstName: "Kyaw Zaw",
      lastName: "Hein"
    })

    setTimeout(() => {
      state.firstName = "Thu Zar"
      state.lastName = "Nwe"
    }, 2000)

    const count = ref(0)

    function increaseNumber() {
      count.value++
    }

    function changeHero() {
      state.firstName = "Te"
      state.lastName = "Cv"
    }

    return {
      ...toRefs(state),
      count,
      increaseNumber,
      changeHero
    }
  }
}
</script>

<style scoped>
</style>

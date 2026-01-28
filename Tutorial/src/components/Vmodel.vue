<template>
    <div>
        <input type="text" v-model="fName">
        <input type="text" v-model="lName">

        <input type="text" v-model="heroName">
        <input type="text" v-model="firstName">
        <input type="text" v-model="lastName">
    </div>
</template>

<script>
import { ref,reactive, toRefs } from 'vue';

    export default {
        setup(){
            const heroName = ref('')
            const state = reactive({
                firstName: '',
                lastName: ''
            })

            return {
                heroName,
                ...toRefs(state)
            }
        }
    }
</script>

<style scoped>

</style>
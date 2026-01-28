<template>
    <div>
        <h3>{{ firstName }} {{ lastName }}</h3>
    </div>
</template>

<script>
        import  {reactive, toRefs}  from 'vue' 
    export default {

        setup(){
            // let name = ref("Kyaw");
            const state = reactive({
                firstName: "Kyaw Zaw",
                lastName: "Hein",
            })
            
            setTimeout(() => {
                state.firstName = "Thu Zar"
                state.lastName = "Nwe"
                
            },2000)

            return toRefs(state)
            
        },
        data(){
            return {
                fname: "k",
                lname: 'z'
            }
        }

        
    }
</script>

<style scoped>

</style>
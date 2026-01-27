<template>
    <div>
<h3>Hello</h3>
<input ref="inputRef" type="text">
    </div>
</template>

<script>
    export default {
        data(){
            return{

            }
        },
        mounted(){
            this.$refs.inputRef.focus();
        }
    }
</script>

<style scoped>

</style>
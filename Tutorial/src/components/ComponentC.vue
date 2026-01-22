<template>
    <h2>Component C</h2>
    <ComponentE></ComponentE>
</template>

<script>
    import ComponentE  from './ComponentE.vue'
    export default{
        // name: 'ComponentC',
        components: {
            ComponentE
        }
    }
</script>
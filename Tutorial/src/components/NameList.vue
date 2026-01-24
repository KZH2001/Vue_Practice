<template>
<div v-for="name in Names" v-bind:key="name.firstName" > 
    <slot :firstName09="name.firstName" :lastName = name.lastName></slot>
</div>
</template>

<script>

export default{
    data(){
        return{
        Names: [
            {firstName: 'K', lastName: 'a'},
             {firstName: 's', lastName: 'e'},
              {firstName: 'e', lastName: 'g'},
               {firstName: 't', lastName: 'g'},
                {firstName: 'K', lastName: 'h'},
        ]
        }
        
    },
}

</script>
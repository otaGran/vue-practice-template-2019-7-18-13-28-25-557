<template>
    <div>
        {{notused}}
    </div>

</template>

<script>
    export default {
        name: "CounterSum",
        data(){
            return{
                sum : 0
            }
        },
        props:{
            notused: Number
        }
    }
</script>

<style scoped>

</style>

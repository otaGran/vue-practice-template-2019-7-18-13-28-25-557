<template>
    <ol>
        <li>
                <span>
     <input type="button" value="+" @click="addCount">
     {{ffcount}}
     <input type="button" value="-" @click="subCount">
   </span>
        </li>
    </ol>

</template>

<script>

    export default {

        name: "CounterGroup",

        methods: {
            addCount() {
                this.ffcount++;
                this.$store.commit('increment');
            },
            subCount() {
                this.ffcount--;
                this.$store.commit('decrement');
            }
        },
        data(){
            return {
                ffcount: 0
            }
        },
        props: {

            counterNum: Number
        },
        beforeDestroy: function () {
            this.$emit('destory', this.count);
            this.$store.commit('destoryItem',this.ffcount);
        },
    }
</script>

<style scoped>

</style>

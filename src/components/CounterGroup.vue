<template>
    <ol>
        <li>
                <span>
     <input type="button" value="+" @click="addCount">
     {{count}}
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
                this.count++;
                this.$emit('addOrSub', 1);
            },
            subCount() {
                this.count--;
                this.$emit('addOrSub', -1);
            }
        },
        data(){
            return {
                count: 0
            }
        },
        props: {

            counterNum: Number
        },
        beforeDestroy: function () {
            this.$emit('destory', this.count);
        },
    }
</script>

<style scoped>

</style>

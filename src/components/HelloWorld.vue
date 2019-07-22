<template>
    <div class="hello">

        <!--     <input type="button" value="+" @click="addCount">-->
        <input type="number" v-model.number="counterNum">
        <span v-for="n in counterNum">

        <CounterGroup v-bind:key="n" @addOrSub="addOrSub" @destory="destoryItem"></CounterGroup>
            </span>

        <CounterSum ></CounterSum>




        <!--     <input type="button" value="-" @click="subCount">-->

    </div>
</template>

<script>
    import CounterGroup from "./CounterGroup";
    import CounterSum from "./CounterSum";

    export default {
        name: 'HelloWorld',
        data() {
            return {
                counterNum :0,
                notused: 0
            }
        },
        methods: {
            addCount() {
                this.count++;
            },
            subCount() {
                this.count--;
            },
            addOrSub(payload) {
                this.notused += payload;
            },
            destoryItem(payload) {
                this.notused -= payload;
            }
        },
        props: {


        }, components: {
            CounterGroup
            , CounterSum
        },


    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>

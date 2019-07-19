<template>
    <div class="hello">

        <!--     <input type="button" value="+" @click="addCount">-->
        <input type="number" v-model.number="counterNum" v-on:change="printCounter()">
        <span v-for="n in counterNum">

        <CounterGroup v-bind:key="n" @addOrSub="addOrSub" @destory="destoryItem"></CounterGroup>
            </span>

        <CounterSum v-model.number="notused"></CounterSum>

        {{notused}}
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

            counterNum: Number
        }, components: {
            CounterGroup
            , CounterSum
        }

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

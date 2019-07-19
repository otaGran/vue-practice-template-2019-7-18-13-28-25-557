<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <HelloWorld v-bind:counterNum="counter"/>
<!--        <CounterGroup  v-bind:counterNum="counter"></CounterGroup>-->
    </div>
</template>

<script>
    import HelloWorld from './components/HelloWorld.vue'
    import CounterGroup from "./components/CounterGroup";

    export default {
        name: 'app',
        data(){
            return {
                counter: 0
            }
        },
        components: {

            HelloWorld
        }

    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>

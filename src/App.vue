<template>
    <div id="app">
        <LandingPage />
    </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";
import LandingPage from './components/Landing.vue';

@Component({
    components: {
        HelloWorld,
        LandingPage,
    }
})
export default class App extends Vue {}
</script>

<style lang="scss">
#app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;

    display: flex;
    justify-content: center;
    align-items: center;

    width: 100vw;
    height: 100vh;



}
</style>

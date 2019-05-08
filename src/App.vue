<template>
    <div id="app">
        <transition  name="fade" mode="out-in">
            <LandingPage  v-if="activeIndex === 0" v-on:done="increment" class="page"/>
        </transition>

        <transition name="bounce">
            <DearMom    v-if="activeIndex === 1" @click.native="increment" class="page"/>
        </transition>

        <transition name="slideUp">
            <AboutPage    v-if="activeIndex === 2"  @click.native="increment"  class="page"/>
        </transition>

        <transition name="slideDown">
            <Amazing    v-if="activeIndex === 3"  v-on:done="increment"  class="page"/>
        </transition>

        <transition name="fadeUp">
            <ThickThin    v-if="activeIndex === 4"  @click.native="increment" class="page"/>
        </transition>

        <transition name="fade">
            <Love    v-if="activeIndex === 5"  v-on:done="increment"   class="page"/>
        </transition>

        <transition name="fade">
            <LeavingPage    v-if="activeIndex === 6"  class="page"/>
        </transition>

        <footer>Made with <img src="./assets/heart.png" style="width: 1rem; margin-top:0.5rem"/> by 
            <a href="https://olivermharrison.com/" target="_blank">olivermharrison</a>   
        </footer>

        <div class="controls">
            <img src="./assets/left-chevron.png" @click="increment(-1)" v-if="activeIndex != 0"/>
            <img src="./assets/reset.png" @click="increment(activeIndex * -1)" />
            <img src="./assets/right-chevron.png" @click="increment(1)"/>
        </div>
        
    </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";
import LandingPage from './components/Landing.vue';
import LeavingPage from './components/Leaving.vue';
//import  from "./components/.vue";
import DearMom from "./components/DearMom.vue";
import AboutPage from "./components/About.vue";
import Amazing from "./components/Amazing.vue";
import ThickThin from "./components/ThickThin.vue";
import Love from "./components/Love.vue";

@Component({
    components: {
        HelloWorld,
        LandingPage,
        DearMom,
        LeavingPage,
        AboutPage,
        Amazing,
        ThickThin,
        Love,
    }
})
export default class App extends Vue {
    public activeIndex = 0;

    public isAnimating = false;

    public increment(value: number = 1) {
        if (this.isAnimating) {
            return;
        }
        const previousIndex = this.activeIndex;
        this.activeIndex = -1;
        this.isAnimating = true;
        setTimeout(() => {
            this.activeIndex = previousIndex + value;
            setTimeout(() => {
                this.isAnimating = false;
            }, 1000);
        }, 1000);
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Poppins:200,400,700');
#app {
    font-family: 'Poppins', "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;

    .controls {
        position: absolute;
        right: 0;
        top: 0;
        img {
            padding: 1rem;
            width: 2.5rem;
            cursor: pointer;
        }
    }
}

.page {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    width: 100vw;
    height: 100vh;
}

html, body, #app, .page {
    overflow: hidden;
}

* {
    user-select: none;
}

p {
    font-size: 1rem;
    max-width: 40rem;
    padding: 1rem;
}
span {
    font-size: 1rem;
}

img {
    max-width: 10rem;
}

footer {
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    padding: 0.5rem;
}


.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>

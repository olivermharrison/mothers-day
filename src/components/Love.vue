<template>
    <div @click="$emit('done')">
        <img v-for="(heart, index) in hearts" 
            :key="index" 
            src="../assets/heart.png"
            :style="heart"
            class="heart animated pulse infinite"/>
        <p>All my love, <br><br>Oliver</p>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Love extends Vue {

    public loop: any;

    public hearts: any = [];

    public mounted() {
        this.loop = setInterval(() => {
            this.hearts.push({
                top: window.innerWidth * Math.random() + 'px',
                left: window.innerHeight * Math.random() + 'px',
                width: Math.floor(100 * Math.random()) + 'px',
            });
        }, 100);
    }

    public beforeDestroy() {
        clearInterval(this.loop);
    }
}
</script>

<style scoped lang="scss">

.heart {
    position: fixed;
}

p {
    z-index: 1000;
    border-radius: 1rem;
    font-size: 2.5rem;
    font-weight: bolder;
}
</style>

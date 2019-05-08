<template>
    <div>
        <p>You've been with me through</p>
        <span :class="{bold: activeIndex > 0}" style="font-weight: bolder">THICK</span>
        <p>and</p>
        <span :class="{light: activeIndex > 1}" style="font-weight: lighter">AND THIN</span>

        <br>
        <p> and I am so very grateful for that.</p>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class ThickThin extends Vue {
    public activeIndex = 0;

    public mounted() {
        setTimeout(() => {
            this.activeIndex++;
        }, 1000);
        setTimeout(() => {
            this.activeIndex++;
        }, 2000);
    }
}
</script>

<style scoped lang="scss">

span {
    font-size: 3rem;

    transition: all 1s;

    &.bold {
        transform: scaleX(2);
    }
    &.light {
        transform: scaleX(0.5);
    }
}
</style>

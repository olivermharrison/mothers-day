<template>
    <div @click="open()">
        <img src="../assets/envelope.png" class="animated pulse slow" :class="{bounceOut: isOpened, infinite: !isOpened}"/>
        <p class="animated"  :class="{fadeOut: isOpened}">Tap to open.</p>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class LandingPage extends Vue {

    public isOpened = false;

    public open() {
        this.isOpened = true;
    }
}
</script>

<style scoped lang="scss">
    img {
        width: 10rem;
    }
</style>

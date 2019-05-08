<template>
    <div @click="open()">
        <img src="../assets/envelope.png" class="animated pulse slow" :class="{bounceOut: isOpened, infinite: !isOpened}"/>
        <br>
        <span class="animated  "  :class="{fadeOut: isOpened}">Tap to open.</span>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class LandingPage extends Vue {

    public isOpened = false;

    public open() {
        this.isOpened = true;
        setTimeout(() => {this.$emit('done')}, 1000);
    }
}
</script>

<style scoped lang="scss">
    img {
        width: 10rem;
    }
</style>

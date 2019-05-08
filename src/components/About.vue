<template>
    <div>
        <p>This year I thought I'd do something a bit different for Mother's Day, so I built you this. </p>
        <br>
        <img src="../assets/kiss.png" class="animated bounceInDown delay-1s"/>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class About extends Vue {

}
</script>

<style scoped lang="scss">
img {
    width: 7rem;
}
</style>

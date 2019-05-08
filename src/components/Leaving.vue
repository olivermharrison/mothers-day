<template>
    <div>
        <p>

            Dear Mom, 
            <br><br>
            This year I thought I'd do something a bit different for Mother's Day, so I built you this.
            <br><br>
            Happy Mothers day to the most amazing woman I know. 
            <br><br>
            You've been with me through thick and thin, and I am so very grateful for that. 

            <br><br>
            All my love, <br>Oliver
        </p>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class LeavingPage extends Vue {

}
</script>

<style scoped lang="scss">
div {
    width: 100%;
    height: 100%;
    p {
        padding: 4rem;
        font-size: 1.2rem;
        overflow: auto;
    }
}
</style>

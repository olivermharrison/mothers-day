<template>
    <div>
        <h1>Dear Mom</h1>
        
        <span class="animated fadeIn delay-2s">(tap to continue)</span>
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class DearMom extends Vue {

}
</script>

<style scoped lang="scss">
h1 {
    font-size: 5rem;
}
</style>

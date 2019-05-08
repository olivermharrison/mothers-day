<template>
    <div @click="nextWord()">
        <p>
            Happy Mothers day to the most 
        </p>
        <transition name="bounceDown">
            <h1 v-if="activeIndex >= 0">
                {{adjectives[activeIndex]}}
            </h1>
        </transition>
        

        <p>woman I know.</p>
        
    </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Amazing extends Vue {

    public adjectives = [
        "AMAZING",
        "THOUGHTFULL",
        "CARING",
        "CONSIDERATE",
        "INCREDIBLE",
    ];

    public activeIndex = 0;


    public nextWord() {
        if (this.activeIndex + 1 < this.adjectives.length) {
            const currentIndex = this.activeIndex;
            this.activeIndex = -1;
            setTimeout(() => {
                this.activeIndex = currentIndex + 1;
            }, 500);
            
        } else {
            this.$emit('done');
        }
        
    }


}
</script>

<style scoped lang="scss">

</style>

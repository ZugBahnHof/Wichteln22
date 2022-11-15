<template>
  <div class="snowflake-wrapper"><SnowFlakes v-if="!reducedMotion" /></div>
  <GiftBox :open="open"/>
  <GiftInput/>
  <input type="checkbox" v-model="open">
</template>

<script>
import SnowFlakes from "@/components/SnowFlakes";
import GiftBox from "@/components/GiftBox";
import GiftInput from "@/components/GiftInput";

export default {
  name: 'App',
  components: {
    GiftBox,
    GiftInput,
    SnowFlakes,
  },
  data: () => {return {
    open: true,
    reducedMotion: false,
  }}
}
</script>

<style>
  #app {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;
    min-width: 100vw;
    justify-content: space-evenly;
  }
  .snowflake-wrapper {
    height: 100vh;
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
    overflow: clip;
    pointer-events: none;
  }
</style>

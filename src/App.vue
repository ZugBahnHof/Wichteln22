<template>
  <GiftBox :open="open"/>
  <input type="checkbox" v-model="open" @click="open = !open">
<!--  <HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <div class="snowflake-wrapper"><SnowFlakes v-if="!reducedMotion" /></div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import SnowFlakes from "@/components/SnowFlakes";
import GiftBox from "@/components/GiftBox";

export default {
  name: 'App',
  components: {
    GiftBox,
    // HelloWorld,
    SnowFlakes,
  },
  data: () => {return {
    open: true,
    reducedMotion: true,
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
  }
</style>

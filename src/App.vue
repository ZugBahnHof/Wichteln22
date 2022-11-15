<template>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <div class="snowflake-wrapper"><SnowFlakes /></div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import SnowFlakes from "@/components/SnowFlakes";

export default {
  name: 'App',
  components: {
    HelloWorld,
    SnowFlakes,
  }
}
</script>

<style>
  .snowflake-wrapper {
    height: 100vh;
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
    overflow: clip;
  }
</style>

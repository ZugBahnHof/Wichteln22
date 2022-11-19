<template>
  <div class="snowflake-wrapper"><SnowFlakes v-if="!reducedMotion" /></div>
  <SnowBorder/>
  <DottingTitle/>
  <GiftBox :open="inputCorrect" name="Jonerthan"/>
  <GiftInput v-model="input"/>
</template>

<script>
import SnowFlakes from "@/components/SnowFlakes";
import GiftBox from "@/components/GiftBox";
import GiftInput from "@/components/GiftInput";
import DottingTitle from "@/components/DottingTitle";
import SnowBorder from "@/components/SnowBorder";

export default {
  name: 'App',
  components: {
    DottingTitle,
    GiftBox,
    GiftInput,
    SnowFlakes,
    SnowBorder,
  },
  data: () => {return {
    reducedMotion: false,
    input: "",
  }},
  computed: {
    inputCorrect() {
      return this.input.toLowerCase() === "passwort";
    }
  }
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

  * {
    font-family: "Dancing Script", "Caveat", "Indie Flower", "Permanent Marker", "XKCHAND", "Gloria Hallelujah", "Purisa", "Century Schoolbook L", "Comic Sans MS", sans-serif;
  }
</style>

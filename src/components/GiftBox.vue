<template>
  <div class="box" :data-open="open">
    <span id="name" v-text="name"></span>
    <div class="front"></div>
    <div class="lid"></div>
  </div>
</template>

<script>
export default {
  name: "GiftBox",
  props: {
    open: {
      type: Boolean,
      required: false,
      default: false,
    },
    name: {
      type: String,
      required: false,
      default: null,
    },
  }
}
</script>

<style scoped>
  .box {
    position: relative;
    content: "";
    aspect-ratio: 1;
    width: clamp(300px, 75vmin, 900px);
  }
  .box div {
    content: "";
    aspect-ratio: 1;
    /*background: red;*/
    position: absolute;
    left: 50%;
    transform: translate(-50%);
    transition: all 2s ease;
    border-radius: 2px;
  }
  .box .front {
    width: clamp(200px, 50vmin, 600px);
    background-image: linear-gradient(transparent 40%, green 40%, green 60%, transparent 60%),
                      linear-gradient(to right, transparent 40%, green 40%, green 60%, transparent 60%);
    background-color: red;
    top: 50%;
    transform: translate(-50%, -50%);
  }

  .box .lid {
    width: clamp(220px, 55vmin, 660px);
    height: clamp(40px, 10vmin, 120px);
    background-image: linear-gradient(to right, transparent 37%, green 37%, green 63%, transparent 63%);
    background-color: red;
    top: 50%;
    left: 50%;
    box-shadow: 0 3px 2px -2px rgba(128, 0, 0, 1), inset 0 20px 5px -12px rgba(226, 226, 226, 1);
    transform: translate(-50%, clamp(-330px, -27.5vmin, -110px));
  }

  .box[data-open="true"] .front {
    transform: translate(-75%, 0%) rotate(30deg);
  }

  .box[data-open="true"] .lid {
    transform: translate(-60%, calc(-50% + clamp(-330px, -27.5vmin, -110px))) rotate(-30deg);
  }

  #name {
    color: white;
    font-family: Purisa, Comic Sans MS, Roboto, Montserrat, sans-serif;
    position: absolute;
    left: 25%;
    top: 50%;
    transform: scale(20%) rotate(-45deg);
    font-size: clamp(40px, 10vmin, 120px);
    transition: all ease-in-out 2s;
  }

  .box[data-open="true"] #name {
    transform: none;
    left: 50%;
    top: 25%;
  }
</style>
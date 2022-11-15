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
  },
  data() {
    return {
      min: 150,
      vvv: 50,
      max: 400,
    }
  }
}
</script>

<style scoped>
  .box {
    position: relative;
    content: "";
    aspect-ratio: 1;
    width: clamp(calc(3px / 2 * v-bind(min)), calc(3vmin / 2 * v-bind(vvv)), calc(3px / 2 * v-bind(max)));
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
    width: clamp(calc(1px * v-bind(min)), calc(1vmin * v-bind(vvv)), calc(1px * v-bind(max)));
    background-image: linear-gradient(transparent 40%, green 40%, green 60%, transparent 60%),
                      linear-gradient(to right, transparent 40%, green 40%, green 60%, transparent 60%);
    background-color: red;
    top: 50%;
    transform: translate(-50%, -50%);
  }

  .box .lid {
    width: clamp(calc(11px / 10 * v-bind(min)), calc(11vmin / 10 * v-bind(vvv)), calc(11px / 10 * v-bind(max)));;
    height: clamp(calc(1px / 5 * v-bind(min)), calc(1vmin / 5 * v-bind(vvv)), calc(1px / 5 * v-bind(max)));
    background-image: linear-gradient(to right, transparent 37%, green 37%, green 63%, transparent 63%);
    background-color: red;
    top: 50%;
    left: 50%;
    box-shadow: 0 3px 2px -2px rgba(128, 0, 0, 1), inset 0 20px 5px -12px rgba(226, 226, 226, 1);
    transform: translate(-50%, clamp(calc(-11px / 20 * v-bind(max)), calc(-11vmin / 20 * v-bind(vvv)), calc(-11px / 20 * v-bind(min))));
  }

  .box[data-open="true"] .front {
    transform: translate(-75%, 0%) rotate(30deg);
  }

  .box[data-open="true"] .lid {
    transform: translate(-60%, calc(-50% + clamp(calc(-11px / 20 * v-bind(max)), calc(-11vmin / 20 * v-bind(vvv)), calc(-11px / 20 * v-bind(min))))) rotate(-30deg);
  }

  #name {
    color: white;
    font-family: Purisa, Comic Sans MS, Roboto, Montserrat, sans-serif;
    position: absolute;
    left: 25%;
    top: 50%;
    transform: scale(20%) rotate(-45deg);
    font-size: clamp(calc(1px / 5 * v-bind(min)), calc(1vmin / 5 * v-bind(vvv)), calc(1px / 5 * v-bind(max)));
    transition: all ease-in-out 2s;
  }

  .box[data-open="true"] #name {
    transform: none;
    left: 50%;
    top: 25%;
  }
</style>
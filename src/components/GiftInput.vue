<template>
  <div class="wrapper">
    <div class="tag">
      <input type="text" name="name-input" id="name-input" :value="modelValue"
             @input="$emit('update:modelValue', $event.target.value)" placeholder="Enter your code..."
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "GiftInput",
  props: {
    modelValue: String,
  },
  emits: ["update:modelValue"],
}
</script>

<style scoped>
.wrapper {
  background: #e09514;
  padding: .5em;
  border-radius: 2px;
}
.tag {
  height: 100px;
  padding: 2em;
  position: relative;
  --mask:
      radial-gradient(1em at 1em 1em,#0000 calc(98% - 0.25em),#000 calc(100% - 0.25em) 98%,#0000) -1em -1em,
      linear-gradient(90deg,#000 0.5em,#0000 0) -0.25em 50% /100% calc(100% - 2em + 0.25em) repeat-x,
      linear-gradient(      #000 0.5em,#0000 0) 50% -0.25em/calc(100% - 2em + 0.25em) 100% repeat-y;
}
.tag:before {
  content: "";
  position: absolute;
  inset: 0;
  background: green;
  -webkit-mask: var(--mask);
  mask: var(--mask);
  pointer-events: none;
}

input {
  border: none;
  padding: 1em;
  border-radius: 12px;
  color: whitesmoke;
  width: 100%;
  transition: background-position ease 2s;
  background: #ad730f linear-gradient(75deg, transparent 20%, white 30%, transparent 40%) no-repeat fixed;
  background-size: 100%;
  background-position-x: -100vw;
}

input:focus {
  outline: green 1px solid;
  background-position-x: 100vw;
}
</style>
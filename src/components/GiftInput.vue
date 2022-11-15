<template>
  <div class="wrapper">
<!--    <div class="triangle"></div>-->
    <div class="tag">
      <input type="text" name="name-input" id="name-input" :value="modelValue"
             @input="$emit('update:modelValue', $event.target.value)">
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
  position: relative;
}
.tag {
  background: #e09514;
  height: 100px;
  padding: 2em 2em 2em calc(2em + 25%);

  -webkit-clip-path: polygon(25% 0%, 100% 0, 100% 100%, 25% 100%, 0% 50%);
  clip-path: polygon(25% 0%, 100% 0, 100% 100%, 25% 100%, 0% 50%);
  box-shadow: inset 0 20px 5px -12px rgba(226, 226, 226, 1);
  border-radius: 2px;
}

input {
  background: #ad730f;
  border: none;
  padding: 1em;
  border-radius: 12px;
  color: whitesmoke;
  width: 100%;
}
</style>
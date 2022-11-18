<template>
  <h1>Besorge ein Geschenk für</h1>
</template>

<script>
export default {
  name: "DottingTitle"
}
</script>

<style scoped>
h1 {
  color: white;
  text-align: center;
  word-break: break-word;
  hyphens: auto;
}

@keyframes dots {
  0% {
    content: "";
  }
  25% {
    content: ".";
  }
  50% {
    content: "..";
  }
  75% {
    content: "...";
  }
}

h1:after {
  content: "";
  animation: dots ease-in-out infinite 2s;
  width: 3ch;
  display: inline-block;
  text-align: left;
}
</style>
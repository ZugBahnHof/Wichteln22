<template>
  <div class="wrapper">
    <span v-for="n in 400" :key="n">❄</span>
  </div>
</template>

<script>
export default {
  name: "SnowBorder"
}
</script>

<style scoped lang="scss">
  .wrapper {
    position: absolute;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    overflow: clip;
    pointer-events: none;
  }

  span {
    position: absolute;
    color: white;
    pointer-events: none;

    $inline-offset: 200;
    $center-foo: 70;
    $size: 15;

    @for $i from 1 through 400 {
      &:nth-child(#{$i}) {
        $s: unquote(random($size) + "em");
        font-size: $s;
        //line-height: $s;
        opacity: random() * 0.6;
      }
    }

    @for $i from 1 through 100 {
      &:nth-child(#{$i}) {
        left: unquote(random(10) + "vw");
        top: unquote(random(100) + "vh");
        transform: translate(-80%, -50%);
      }
    }

    @for $i from 101 through 200 {
      &:nth-child(#{$i}) {
        right: unquote(random(10) + "vw");
        top: unquote(random(100) + "vh");
        transform: translate(+80%, -50%);
      }
    }

    @for $i from 201 through 300 {
      &:nth-child(#{$i}) {
        left: unquote(random(100) + "vw");
        top: unquote(random(10) + "vh");
        transform: translate(-50%, -80%);
      }
    }

    @for $i from 301 through 400 {
      &:nth-child(#{$i}) {
        left: unquote(random(100) + "vw");
        bottom: unquote(random(10) + "vh");
        transform: translate(-50%, +80%);
      }
    }
  }
</style>
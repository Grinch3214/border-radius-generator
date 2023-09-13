<template>
  <section class="generator">
    <div class="generator__show"></div>
    <input type="range" class="generator__handler" v-model="sliderValue">
		<p>{{ sliderValue }}</p>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const isDragging = ref(false)
const sliderValue = ref(50)

</script>

<style lang="scss" scoped>
.generator {
  position: relative;
  width: 50vh;
  height: 50vh;
  margin: 0 auto;
  border: 2px dashed rgb(211, 142, 15);

  &__show {
    width: 100%;
    height: 100%;
    background: linear-gradient(
      35deg,
      rgba(8, 0, 134, 1),
      rgba(0, 0, 0, 1) 50%,
      rgba(121, 9, 111, 1) 100%
    );
    border-radius: 50% 50% 74% 26% / 31% 44% 56% 69%;
  }

  &__handler {
    position: absolute;
		width: 100%;
    top: 0;
    left: 0;
    // width: 1.8rem;
    // height: 1.8rem;
    // border-radius: 50%;
    // background: #000;
    // border: 3px solid white;
    // cursor: pointer;
    // transition: left 0.2s;
  }
}
</style>

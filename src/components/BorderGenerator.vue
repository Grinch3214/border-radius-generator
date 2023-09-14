<template>
  <section class="generator">
    <div class="generator__show"></div>
    <input type="range" class="generator__handler slider-top" v-model="sliderTopValue">
		<input type="range" class="generator__handler slider-bottom" v-model="sliderBottomValue">
		<input type="range" class="generator__handler slider-left">
		<input type="range" class="generator__handler slider-right">
  </section>
</template>

<script setup>
import { ref } from 'vue';

const sliderTopValue = ref(50)
const sliderBottomValue = ref(50)

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

		&.slider-top {
			top: -10px;
			left: 0;
		}

		&.slider-bottom {
			left: 0;
			bottom: 8px;
		}

		&.slider-left {
			top: 0;
    	left: 7px;
			transform: rotate(90deg);
			transform-origin: 0 0 0;
		}

		&.slider-right {
			bottom: 0;
			right: -10px;
			transform: rotate(90deg);
			transform-origin: 100% 0 0;
		}
  }
}
</style>

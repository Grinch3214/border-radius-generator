<template>
  <section class="generator">
    <div class="generator__show"></div>
    <span
      class="generator__handler"
      :style="{ left: sliderValue + '%' }"
      @mousedown="startDrag"
    ></span>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const isDragging = ref(false);
const sliderValue = ref(50);

function startDrag(event) {
  if (event.button !== 0) return;
  const slider = event.target;
  const rect = slider.getBoundingClientRect();
  const minLeft = 0;
  const maxLeft = 100 - (1.8 / rect.width) * 100; // 1.8 - ширина .generator__handler

  isDragging.value = true;
  let prevX = event.clientX; // Сохраняем начальное положение мыши

  const handleDrag = (e) => {
    if (isDragging.value) {
      const deltaX = e.clientX - prevX;
      const posX = (e.clientX - rect.left) / rect.width;
      const newValue = Math.min(maxLeft, Math.max(minLeft, posX * 100));

      // Добавляем ограничение для минимального перемещения
      if (Math.abs(deltaX) >= 2) { // Измените это значение по вашему усмотрению
        sliderValue.value = newValue;
        prevX = e.clientX;
      }
    }
  };

  const stopDrag = () => {
    isDragging.value = false;
    window.removeEventListener('mousemove', handleDrag);
    window.removeEventListener('mouseup', stopDrag);
  };

  window.addEventListener('mousemove', handleDrag);
  window.addEventListener('mouseup', stopDrag);
}
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
    top: 0;
    left: -0.9rem;
    width: 1.8rem;
    height: 1.8rem;
    border-radius: 50%;
    background: #000;
    border: 3px solid white;
    cursor: pointer;
    transition: left 0.2s;
  }
}
</style>

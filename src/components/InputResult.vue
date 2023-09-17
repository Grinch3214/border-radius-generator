<template>
	<section class="styles">
		<div class="styles__input"><span>border-radius:</span>{{ stylesHandle }}</div>
		<div class="styles__btn">COPY</div>
	</section>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
	ranges: {
		type: Object
	}
})


const calculateValue = (slideValue) => {
	if(slideValue >= 0 && slideValue <= 100) {
		const result = 100 - slideValue
		return result
	}
}

const stylesHandle = computed(() => {
	return `
		${props.ranges.sliderTopValue}%
		${calculateValue(props.ranges.sliderTopValue)}%
		${calculateValue(props.ranges.sliderBottomValue)}%
		${props.ranges.sliderBottomValue}% /
		${props.ranges.sliderLeftValue}%
		${props.ranges.sliderRightValue}%
		${calculateValue(props.ranges.sliderRightValue)}%
		${calculateValue(props.ranges.sliderLeftValue)}%
	`
})
</script>

<style lang="scss" scoped>
	.styles {
		justify-content: center;
		display: flex;
		align-items: center;
		padding: 4rem 0 2rem;

		&__input {
			padding: 1.4rem;
			background: rgb(165, 156, 156);
			border-radius: 8px 0 0 8px;
			color: #111;

			span {
				text-transform: uppercase;
				font-weight: 800;
				color: rgb(9, 4, 68);
			}
		}

		&__btn {
			padding: 1.4rem;
			background: rgb(121, 9, 111);
			border-radius: 0 8px 8px 0;
			cursor: pointer;
			transition: .2s ease;

			&:hover {
				background: rgb(8, 0, 134);
			}
		}
	}
</style>
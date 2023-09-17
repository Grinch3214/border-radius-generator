<template>
	<section class="styles">
		<div class="styles__input"><span>border-radius:</span>{{ stylesHandle }}</div>
		<div class="styles__btn" @click="copyResult">COPY</div>
		<div class="styles__copy" v-if="copied" :style="{'border-radius': stylesHandle }">
			COPIED!
		</div>
	</section>
</template>

<script setup>
import { ref, computed } from 'vue'

const copied = ref(false)

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

async function copyResult() {
	let copyText = `border-radius: ${stylesHandle.value.split(/\s+/).join('')};`
	await navigator.clipboard.writeText(copyText)
	copied.value = true
	setTimeout(() => {
		copied.value = false
	}, 1000)
}
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

		&__copy {
			position: fixed;
			top: 30%;
			left: 50%;
			transform: translateX(-50%);
			background: #111;
			padding: 3rem 4.5rem;
			border-radius: 8px;
			text-transform: uppercase;
			box-shadow: 0 0 18px 1px rgb(121, 9, 111);
		}
	}
</style>
<template>
	<div class="container">
		<HeaderComponent :header="header" />
		<main>
			<BorderGenerator :ranges="ranges" />
			<InputResult :ranges="ranges" />
		</main>
		<FooterComponent :footer="footer" />
	</div>
  
</template>

<script setup>
import { ref } from 'vue'
import HeaderComponent from './components/HeaderComponent.vue'
import BorderGenerator from './components/BorderGenerator.vue'
import InputResult from './components/InputResult.vue'
import FooterComponent from './components/FooterComponent.vue';

const header = ref({
	title: 'Border Radius Generator'
})

const URL = 'https://github.com/Grinch3214'
const currentDate = new Date();
const currentYear = currentDate.getFullYear();

const footer = ref({
	link: URL,
	year: currentYear
})

const ranges = ref({
	sliderTopValue: 35,
	sliderBottomValue: 20,
	sliderLeftValue: 50,
	sliderRightValue: 40
})
</script>

<style lang="scss">
@font-face {
	font-family: 'Open Sans';
	src: url('./assets/fonts/OpenSans-Regular.woff2') format('woff2');
	font-weight: 400;
	font-style: normal;
	font-display: swap;
}

@font-face {
	font-family: 'Open Sans';
	src: url('./assets/fonts/OpenSans-SemiBold.woff2') format('woff2');
	font-weight: 600;
	font-style: normal;
	font-display: swap;
}

@font-face {
	font-family: 'Open Sans';
	src: url('./assets/fonts/OpenSans-ExtraBold.woff2') format('woff2');
	font-weight: 800;
	font-style: normal;
	font-display: swap;
}
</style>


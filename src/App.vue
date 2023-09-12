<template>
	<div class="container">
		<header class="header">
			<h1 class="title">Border Radius Generator</h1>
		</header>
		<main>
			<BorderGenerator />
		</main>
	</div>
  
</template>

<script setup>
import BorderGenerator from './components/BorderGenerator.vue';

	
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
.header {
	padding: 2.5rem 0;
}
</style>


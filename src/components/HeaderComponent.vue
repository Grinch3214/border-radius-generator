<template>
	<header class="header">
		<h1 class="title">{{ props.header.title }}</h1>
	</header>
</template>

<script setup>

const props = defineProps({
	header: {
		type: Object,
	}
})
</script>

<style lang="scss">

.header {
	padding: 2.5rem 0;
}
</style>
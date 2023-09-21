<template>
	<footer class="footer">
		Made with ❤️  <a :href="link" target="_blank">GitHub</a> (c){{ props.footer.year }}
	</footer>
</template>

<script setup>
 const props = defineProps({
	footer: {
		type: Object
	}
 })

 const link = `${props.footer.link}/border-radius-generator`
</script>

<style lang="scss" scoped>
	.footer {
		padding: 20px 0;
		text-align: center;
		background: #000;
		position: relative;

		a {
			text-decoration: none;
			color: rgb(253, 173, 24);
		}

		&::before, &::after {
			position: absolute;
			content: '';
			top: 0;
			left: 0;
			right: 0;
			height: 100%;
			margin-left: calc(-50vw + 600px);
			background: #000;
			z-index: -1;
		}

		&::after {
			margin-right: calc(-50vw + 600px);
		}
	}
</style>>
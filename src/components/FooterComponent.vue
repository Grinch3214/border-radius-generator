<template>
	<footer class="footer">
		Made with ❤️  <a :href="link" target="_blank">GitHub</a> <span>(c)</span>{{ props.footer.year }}
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
		background: #000;
		position: relative;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 8px;

		a {
			text-decoration: none;
			color: rgb(253, 173, 24);
		}

		span {
			font-size: 1.6rem;
			margin: 0 -6px 0 0;
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
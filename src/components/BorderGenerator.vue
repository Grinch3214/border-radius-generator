.<template>
	<section class="generator">
		<div class="generator__show"></div>
	</section>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.generator {
	width: 50vh;
	margin: 0 auto;
	height: 50vh;
	border: 2px dashed rgb(211, 142, 15);

	&__show {
		width: 100%;
		height: 100%;
		background: linear-gradient(35deg, rgba(8,0,134,1), rgba(0,0,0,1) 50%, rgba(121,9,111,1) 100%);
		border-radius: 50% 50% 74% 26% / 31% 44% 56% 69%;
	}
}
</style>
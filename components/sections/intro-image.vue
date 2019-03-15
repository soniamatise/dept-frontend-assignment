<template>
	<section :style="`background-image: url('${ image }')`" class="section section__intro-image intro-image">
		<div class="intro-image__title">
			<h2>WORK</h2>
		</div>
		<nuxt-link to="/">
			<button class="button button--full-black">
				View case
			</button>
		</nuxt-link>
	</section>	
</template>

<script>
// import clientLogo from '~/components/elements/client-logo.vue';
export default {
	components: {
		// clientLogo
	},
	props: ['image']

}

</script>


<style lang="scss">
@import '~tools';
.intro-image {
	height: calc(100vh - 30px);
	width: calc(100vw - 30px);
	margin: 15px;
	background-color: color(White)
}
</style>
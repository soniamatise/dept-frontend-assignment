<template>
	<section :style="`background-image: url('${ image }')`" class="intro-image">
		<section class="section intro-image__inner row center">
			<div class="intro-image__title">
				<h2>WORK</h2>
			</div>
			<div class="intro-image__cta">
				<nuxt-link to="/">
					<button class="button button--full-black">
						View case
					</button>
				</nuxt-link>
			</div>
		</section>
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
	width: calc(100% - 40px);
	height: calc(100% - 40px);
	margin: 20px;
	background-color: color(White);
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center center;

	@media #{$medium-down} {
		width: 100%;
		height: 320px;
		margin: 0;
	}

	&__inner {
		height: 100%;
	}
	&__title {
		h3 {
			color: colro(Black);
		}
	}
	&__cta {
		align-self: flex-end;
		@media #{$medium-down} {
			display: none;
		}
	}
}
.row.center.intro-image__inner {
	justify-content: space-between;
	flex-direction: column;
	align-items: space-between;
}
</style>
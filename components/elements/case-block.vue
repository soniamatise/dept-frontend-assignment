<template>
	<section class="row center small-full medium-full large-22 work-together">
		<div class="column">
			<div class="work-together__inner work-together__inner--text">
				<slot />
			</div>
			<div class="work-together__inner work-together__inner--image">
				<img :src="asset" />
			</div>
		</div>
	</section>
</template>

<script>
export default {
	components: {
	},
	props: ['asset']
};
</script>

<style lang="scss">
@import '~tools';
</style>
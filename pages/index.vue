<template>
	<main class="page page--home">
		<section class="section section__cases-archive cases-archive">
			<case-block/>
			<case-block/>
			<case-block/>
			<case-block/>
			<case-block case-type="long"/>
			<div class="cases-archive__short-cases">
				<case-block case-type="short"/>
				<case-block case-type="short"/>
			</div>
			<case-block/>
		</section>
		<clients/>
	</main>
</template>

<script>
import caseBlock from '~/components/elements/case-block.vue';
import clients from '~/components/sections/clients.vue';

export default {
	components: {
		caseBlock,
		clients
	}
};
</script>

<style lang="scss">
@import '~tools';

.page {
	// general page styles
	&--home {
		// specific home styles
	}
}

</style>

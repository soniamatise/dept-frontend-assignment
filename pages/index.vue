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
	},
	data () {
        return {
            clients: [
                { url: require('~/static/images/clients/ABN.png')},
                { url: require('~/static/images/clients/Adidas.png')},
                { url: require('~/static/images/clients/KLM.png')},
                { url: require('~/static/images/clients/Microsoft.png')},
                { url: require('~/static/images/clients/Mona.png')},
                { url: require('~/static/images/clients/Nivea.png')},
                { url: require('~/static/images/clients/NN.png')},
                { url: require('~/static/images/clients/Oxxio.png')},
				{ url: require('~/static/images/clients/Pathe.png')},
				{ url: require('~/static/images/clients/Tomtom.png')},
				{ url: require('~/static/images/clients/Transavia.png')},
				{ url: require('~/static/images/clients/Triumph.png')},
				{ url: require('~/static/images/clients/Unilever.png')},
				{ url: require('~/static/images/clients/Walibi.png')},
				{ url: require('~/static/images/clients/Zalando.png')},
				{ url: require('~/static/images/clients/Ziggo.png')},
            ]
		}
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

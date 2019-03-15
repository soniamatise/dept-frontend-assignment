<template>
	<main class="page page--home">
		<intro-image/>
		<section class="section section__cases-archive cases-archive">
			<case-block/>
			<case-block/>
			<case-block/>
			<case-block/>

			<!-- <div v-for="(item, index) in cases" :key="index" class="clients__logo">
				<img :src="image.url"/>
			</div> -->
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
import introImage from '~/components/sections/intro-image.vue';

export default {
	components: {
		caseBlock,
		clients,
		introImage
	},
	data() {
        return {
			cases: [
                { 
					image: require('~/static/images/cases/bol.png'),
					title: 'A summer island in the Netherlands',
					client: 'bol.com',
					caseLink: '/',
				},
                { 
					image: require('~/static/images/cases/kempen.png'),
					title: 'Not some average banking website',
					client: 'kempen',
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/philips.png'),
					title: 'Beautiful design meets innovative technology',
					client: 'philips',
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/gemeentemuseum.png'),
					title: 'A 100 years of Mondriaan & De Stijl',
					client: 'gemeentemuseum',
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/florensis-1.png'),
					title: 'Rethinking the entire online ecosystem',
					client: 'florensis',
					caseLink: '/',
				},
				{ 
					title: 'Tapping into Ireland’s unique gaming culture and bringing a fresh flavour to their Xbox social media channels',
					client: 'microsoft',
					caseLink: '/',
				},
				{ 
					title: 'Integrating existing content into O’Neill’s new e-commerce platform',
					client: "o'neill",
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/belighting.png'),
					title: 'Delivering clarity on a global scale',
					client: 'be lightning',
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/tui.png'),
					title: 'Swipe to find your next holiday destination',
					client: 'tui',
					caseLink: '/',
				},
				{ 
					title: 'Enhancing customer experience for personalised holiday planning using real time data',
					client: 'butlins',
					caseLink: '/',
				},
				{ 
					title: 'Predicting booking behavior for holidays with smart data, voice search and machine learning',
					client: 'vacanseselect',
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/florensis-1.png'),
					title: 'Rethinking the entire online ecosystem',
					client: 'florensis',
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/chocomel.png'),
					title: 'A campaign for the limited edition letter packs',
					client: 'chocomel',
					caseLink: '/',
				},

				{ 
					image: require('~/static/images/cases/jbl.png'),
					title: 'Live like a champion with Jerome Booteng',
					client: 'jbl',
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/zalando.png'),
					title: 'Innovative SEO and content strategy for Zalando',
					client: 'zalando',
					caseLink: '/',
				},
				{ 
					image: require('~/static/images/cases/bibliotheek.png'),
					title: 'The search for the most influential book ever',
					client: 'koninklijke bibliotheek',
					caseLink: '/',
				},
			],
			items: [
				{ message: 'Foo' },
				{ message: 'Bar' }
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

<template>
	<main class="page page--home row center">
		<!-- <l-header/> -->
		<intro-image :image="headerImg"/>
		<section class="section section__cases-archive cases-archive">
			<case-block v-for="(item, index) in cases.slice(0,4)" :key="index"
				:case-image="item.image"
				:case-client="item.client"
				:case-title="item.title"
				case-link="/"
			/>
			<case-block 
				:case-image="cases[4].image"
				:case-client="cases[4].client"
				:case-title="cases[4].title"
				case-link="/"
				case-type="long"
			/>
			<div class="cases-archive__short-cases">
				<case-block v-for="(item, index) in cases.slice(5,7)" :key="index"
					:case-client="item.client"
					:case-title="item.title"
					case-link="/"
					case-type="short"
				/>
			</div>
			<case-block v-for="(item, index) in cases.slice(7,9)" :key="index"
				:case-image="item.image"
				:case-client="item.client"
				:case-title="item.title"
				case-link="/"
			/>
			<div class="cases-archive__short-cases">
				<case-block v-for="(item, index) in cases.slice(9,11)" :key="index"
					:case-client="item.client"
					:case-title="item.title"
					case-link="/"
					case-type="short"
				/>
			</div>
			<case-block 
				:case-image="cases[11].image"
				:case-client="cases[11].client"
				:case-title="cases[11].title"
				case-link="/"
				case-type="long"
			/>
			<case-block v-for="(item, index) in cases.slice(12,18)" :key="index"
				:case-image="item.image"
				:case-client="item.client"
				:case-title="item.title"
				case-link="/"
			/>
		</section>
		<quote
			:quote-text="quote.text"
			:quote-author="quote.author.name"
			:author-function="quote.author.function"
			:author-company="quote.author.company"
		/>
		<clients/>
		<s-form/>
		<!-- <l-footer/> -->
	</main>
</template>

<script>
import caseBlock from '~/components/elements/case-block.vue';
import clients from '~/components/sections/clients.vue';
import introImage from '~/components/sections/intro-image.vue';
import quote from '~/components/elements/quote.vue';
import sForm from '~/components/sections/s-form.vue';
import lHeader from '~/components/layout/l-header.vue';
import lFooter from '~/components/layout/l-footer.vue';

export default {
	components: {
		caseBlock,
		clients,
		introImage,
		quote,
		sForm,
		lHeader,
		lFooter
	},
	data() {
        return {
			headerImg: require('~/static/images/cases/florensis-1.png'),
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
			quote: {
				text: "Dept helped us tell our story through a bold new identity and a robust online experience. To the tune of 60% growth in online bookings in just one month.",
				author: {
					name: "MATTIJS TEN BRINK",
					function: "ceo",
					company: "transavia",
				}
			},
		}
	}
};
</script>

<style lang="scss">
@import '~tools';

.page {
	&--home {
		width: 100vw;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
}

</style>

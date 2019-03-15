<template>
	<article v-if="caseType == 'short'" class="case-block case-block--short">
		<span class="case-block__client">{{ caseClient }}</span>
		<div class="case-block__title"><h3>{{ caseTitle }}</h3></div>
		<nuxt-link v-if="caseLink" :to="caseLink" class="button button--blue case-block__cta">VIEW CASE</nuxt-link>
	</article>
	<article v-else-if="caseType == 'long'" class="case-block case-block--long">
		<div class="case-block__image">
			<img :src="caseImage">
		</div>
		<span class="case-block__client">{{ caseClient }}</span>
		<div class="case-block__title"><h3>{{ caseTitle }}</h3></div>
		<nuxt-link v-if="caseLink" :to="caseLink" class="button button--blue case-block__cta">VIEW CASE</nuxt-link>
	</article>
	<article v-else class="case-block case-block--normal">
		<div class="case-block__image">
			<img :src="caseImage">
		</div>
		<div class="case-block__description">
			<span class="case-block__client">{{ caseClient }}</span>
			<div class="case-block__title"><h3>{{ caseTitle }}</h3></div>
			<nuxt-link v-if="caseLink" :to="caseLink" class="button button--blue case-block__cta">VIEW CASE</nuxt-link>
		</div>
	</article>
</template>

<script>
export default {
	components: {
	},
	props: ['caseClient', 'caseTitle', 'caseLink', 'caseType', 'caseImage']
};
</script>

<style lang="scss">
@import '~tools';

.case-block {
	background-color:color(WhiteSecond);
	margin: 40px 0;
	&--normal {
		width: calc(50% - 30px);
		height: grid(7 + 2);
	}
	&--long {
		width: calc(70% - 30px);
		height: grid(7 + 2);
	}
	&--short {
		margin: 0;
		width: 100%;
		height: grid(9 / 2);
		border-bottom: 1px solid color(WhiteThird);
	}
	&__description{

	}
	&__image {
		height: grid(7);
		overflow: hidden;
		position: relative;

		img {
			height: 150%;
			position: absolute;
			transition: transform .2s ease;
			transform: translate(-50%,-50%);
			left: 50%;
			top: 50%;
		}
	}
	&__client {
		text-transform: uppercase;
		color: color(WarmGreySecond);
		font-size: 15px;
	}
}
</style>
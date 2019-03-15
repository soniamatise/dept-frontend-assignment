<template>
	<article v-if="caseType == 'short'" class="case-block case-block--short">
		<span class="case-block__client">{{ caseClient }}</span>
		<div class="case-block__title"><h4>{{ caseTitle }}</h4></div>
		<nuxt-link v-if="caseLink" :to="caseLink" class="button button--blue case-block__cta"><span>VIEW CASE</span></nuxt-link>
	</article>
	<article v-else-if="caseType == 'long'" class="case-block case-block--long">
		<div class="case-block__image">
			<img :src="caseImage">
		</div>
		<span class="case-block__client">{{ caseClient }}</span>
		<div class="case-block__title"><h4>{{ caseTitle }}</h4></div>
		<nuxt-link v-if="caseLink" :to="caseLink" class="button button--blue case-block__cta"><span>VIEW CASE</span></nuxt-link>
	</article>
	<article v-else class="case-block case-block--normal">
		<div class="case-block__image draw">
			<img :src="caseImage">
		</div>
		<div class="case-block__description">
			<span class="case-block__client">{{ caseClient }}</span>
			<div class="case-block__title"><h4>{{ caseTitle }}</h4></div>
			<nuxt-link v-if="caseLink" :to="caseLink" class="button button--blue case-block__cta"><span>VIEW CASE</span></nuxt-link>
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
		@media #{$medium-down} {
			width: 100%;
			height: calc(286px + 170px);
		}
	}
	&--long {
		width: calc(70% - 30px);
		height: grid(7 + 2);
		@media #{$medium-down} {
			width: 100%;
		}
	}
	&--short {
		margin: 0;
		width: 100%;
		$grid: grid(4.5);
		height: calc(#{$grid} + 20px);
		border-bottom: 1px solid color(WhiteThird);
		padding-top: 20px;
		@media #{$medium-down} {
			width: 100%;
			height: 170px;
		}
	}
	&__description{
		// padding-top: 20px;
	}
	&__image {
		height: grid(7);
		overflow: hidden;
		position: relative;
		margin-bottom: 20px;
		@media #{$medium-down} {
			width: 100%;
			height: 286px;
		}
		img {
			height: 140%;
			position: absolute;
			transition: transform 1s ease;
			transform: translate(-50%,-50%);
			left: 50%;
			top: 50%;
			@media #{$medium-down} {
				width: 110%;
				height: auto;
			}
		}
	}
	&__title {
		padding-bottom: 15px;
	}
	&__client {
		text-transform: uppercase;
		color: color(WarmGreySecond);
		font-size: 15px;
		padding-bottom: 10px;
	}
}

.case-block {
	&:hover {
		.case-block__image img {
			transform: translate(-50%, -50%) rotate(5deg) scale(1.2);
		}
		.case-block__cta span {
			left: 20px;
		}
		.work-introduction__overlay-bg {
			opacity: 0.5;
		}
	}
}

</style>
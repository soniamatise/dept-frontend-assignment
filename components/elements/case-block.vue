<template>
	<article v-if="caseType == 'short'" class="case-block case-block--short">
		<div class="case-block__image"/>
		<div class="case-block__client">{{ caseClient }}</div>
		<div class="case-block__client">{{ caseTitle }}</div>
		<nuxt-link v-if="caseLink" :to="caseLink">VIEW CASE</nuxt-link>
	</article>
	<article v-else-if="caseType == 'long'" class="case-block case-block--long">
		<div class="case-block__image"/>
		<div class="case-block__client">{{ caseClient }}</div>
		<div class="case-block__client">{{ caseTitle }}</div>
		<nuxt-link v-if="caseLink" :to="caseLink">VIEW CASE</nuxt-link>
	</article>
	<article v-else class="case-block case-block--normal">
		<div class="case-block__image"/>
		<div class="case-block__client">{{ caseClient }}</div>
		<div class="case-block__client">{{ caseTitle }}</div>
		<nuxt-link v-if="caseLink" :to="caseLink">VIEW CASE</nuxt-link>
	</article>
</template>

<script>
export default {
	components: {
	},
	props: ['caseClient', 'caseTitle', 'caseLink', 'caseType']
};
</script>

<style lang="scss">
@import '~tools';

.case-block {
	background-color:red;
	margin: 40px 0;
	&--normal {
		width: calc(50% - 30px);
		height: grid(8);
	}
	&--long {
		width: calc(70% - 30px);
		height: grid(8);
	}
	&--short {
		margin: 0;
		width: 100%;
		height: grid(4);
		border-bottom: 1px solid color(WhiteThird);
	}
}
</style>
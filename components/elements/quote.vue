<template>
	<section class="section section__quote quote">
		<div class="quote__inner">
			<blockquote class="quote__text">
				"{{ quoteText }}"
			</blockquote>
			<span class="quote__author">{{ quoteAuthor }} - {{ authorFunction }}, {{ authorCompany }}</span>
		</div>
	</section>
</template>

<script>
export default {
	components: {
	},
	props: ['quoteText', 'quoteAuthor', 'authorFunction', 'authorCompany']
};
</script>

<style lang="scss">
@import '~tools';

.quote {
	justify-content: center;
	&__inner {
		width: 54%;
		@media #{$medium-down} {
			width: 100%;
		}
	}
	&__author {
		@media #{$medium-down} {
			font-size: 13px;
		}
	}
	blockquote {
		position: relative;
		display: inline-block;
		border: none;
		padding: 0;
		padding: 0 0 17px;
		&::before, &::after {
			display: none;
		}
	}

}

</style>

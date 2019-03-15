<template>
	<header id="header" :class="['header row center', { 'scrolled': scrolled }]">
		<div class="section section__top-nav top-nav">
			<ul class="top-nav__list">
				<li class="top-nav__item">
					<nuxt-link to="/" class="top-nav__link">
						<span class="top-nav__logo">
							<img :src="logo">
						</span>
					</nuxt-link>
				</li>			
				<li class="top-nav__item top-nav__item--menubtn">
					<a @click="toggleMenu()">
						<h5>MENU</h5>
					</a>
				</li>
			</ul>
		</div>

		<section :class="['menu__overlay', { 'active': showMenu }]">
			<div class="menu-wrapper" @click="toggleMenu()">
				<div class="hamburger-menu black animate" />
			</div>
			<nav class="section section__main-nav main-nav row center">
				<ul class="main-nav__list">
					<li class="main-nav__item">
						<nuxt-link to="/" class="main-nav__link">
							<span class="main-nav__text">Home</span>
						</nuxt-link>
					</li>			
					<li class="main-nav__item">
						<nuxt-link to="/work" class="main-nav__link">
							<span class="main-nav__text">werk</span>
						</nuxt-link>
					</li>	
					<li class="main-nav__item">
						<nuxt-link to="/over" class="main-nav__link">
							<span class="main-nav__text">Over</span>
						</nuxt-link>
					</li>	
					<li class="main-nav__item">
						<nuxt-link to="/diensten" class="main-nav__link">
							<span class="main-nav__text">DIensten</span>
						</nuxt-link>
					</li>	
					<li class="main-nav__item">
						<nuxt-link to="/partners" class="main-nav__link">
							<span class="main-nav__text">partners</span>
						</nuxt-link>
					</li>
					<li class="main-nav__item">
						<nuxt-link to="/stories" class="main-nav__link">
							<span class="main-nav__text">stories</span>
						</nuxt-link>
					</li>
					<li class="main-nav__item">
						<nuxt-link to="/vacatures" class="main-nav__link">
							<span class="main-nav__text">vacatures</span>
						</nuxt-link>
					</li>	
				</ul>
			</nav>
		</section>
	</header>
</template>
<script>
export default {
	data() {
		return {
			showMenu: false,
			scrolled: false,
			logo: require('~/static/images/agency/dept.png'),
		};
	},
	created () {
		window.addEventListener('scroll', this.handleScroll);
	},
	destroyed () {
		window.removeEventListener('scroll', this.handleScroll);
	},
	methods: {
		toggleMenu: function () {
			this.showMenu = !this.showMenu;
		},
		handleScroll () {
			this.scrolled = window.scrollY > 0;
			console.log(this.scrolled);
		}
	}
};
</script>

<style lang="scss">
@import '~tools';

.header {
	position: fixed;
	z-index: 4;
	width: 100%;
	padding: 0 20px;
	transition: background-color 600ms ease;

	@media #{$medium-down} {
		background-color: color(WhiteSecond);
	}

	.main-nav {
		max-width: 1400px;
		width: 100%;
		padding: 0 20px;

		&__list {
			width: 100%;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			align-items: right;
			text-align: right;
			margin-top: 147px;
			@media #{$medium-down} {
				margin-top: 100px;
			}
		}
		&__item {
			cursor: pointer;
			border-bottom: 2px solid color(BlackSecond);
		}
		&__text {
			position: relative;
			z-index: 1;
			font-size: 110px;
			font-family: 'Teko';
			font-weight: normal;
			font-style: normal;
			font-stretch: normal;
			line-height: 1;
			@media #{$medium-down} {
				font-size: 50px;
			}
		}
		&__link {
			color: white;
			text-transform: uppercase;
			&.nuxt-link-exact-active {
				.main-nav__text {
					display: flex;
					justify-content: flex-end;
					align-items: center;
					&:before {
						content: '\25b6';
						font-size: 50px;
						@media #{$medium-down} {
							font-size: 20px;
						}
					}
				}
			}
		}
		&__logo {
			img {
				width: 100px;
				transition: width 600ms ease;
			}
		}
	}

	.top-nav {
		max-width: 1400px;
		width: 100vw;
		padding: rem(50) 0 rem(20);
		border-bottom: 1px solid color(Black);
		transition: padding 600ms ease;

		&__list {
			width: 100%;
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			align-items: center;
		}
		&__item {
			cursor: pointer;
		}
		&__text {
			position: relative;
			z-index: 1;
		}
		&__link {
			color: white;
			text-transform: uppercase;
		}
		&__logo {
			img {
				width: 100px;
				transition: width 600ms ease;
			}
		}
	}
	&.scrolled {
		background-color: color(WhiteSecond);

		.top-nav {
			padding: rem(18) 0 rem(20);
			border: none;
			&__logo {
				img {
					width: 60px;
				}
			}
		}
	}
}
.menu {
	&__overlay {
		position: fixed;
		right: 0%;
		top: 0%;
		z-index: 4;
		background-color: color(Black);
		width: 100%;
		height: 100vh;
		justify-content: space-evenly;
		transition: clip-path 0.5s ease-in-out, width 1s ease 1s;
		-webkit-clip-path: polygon(100% 0, 100% 0, 100% 100%, 100% 100%);
		clip-path: polygon(100% 0, 100% 0, 100% 100%, 100% 100%);
		display: flex;
		flex-direction: column;

		&.active {
			-webkit-clip-path: polygon(0 0, 100% 0%, 100% 100%, 0 100%);
			clip-path: polygon(0 0, 100% 0%, 100% 100%, 0 100%);
		}
	}
	&__inner {
		width: 100%;
		text-align: left;
		h4 { color: color(WhiteSecond); }
		&--navigation {
			h4{ font-size: 50px;}
		}
		&--contact {
			h4{
				font-size: 20px;
				&+ h4 {
					margin-top: 0;
				}
			}
		}
	}
}


$bar-width: 20px;
$bar-height: 2px;
$bar-spacing: 10px;

.menu-wrapper {
	position: fixed;
	top: 20px;
	right: 20px;
	margin: auto;
	z-index: 5;
	width: $bar-width;
	height: $bar-height + $bar-spacing*2;
	cursor: pointer;
}

.hamburger-menu,
.hamburger-menu:after,
.hamburger-menu:before {
	width: $bar-width;
	height: $bar-height;
}

.hamburger-menu {
	position: relative;
	transform: translateY($bar-spacing);
	background: color(White);
	transition: all 0ms 300ms;

	&.animate {
		background: rgba(255, 255, 255, 0);
	}
}

.hamburger-menu:before {
	content: "";
	position: absolute;
	left: 0;
	bottom: $bar-spacing;
	background: color(White);
	transition: bottom 300ms 300ms cubic-bezier(0.23, 1, 0.32, 1), transform 300ms cubic-bezier(0.23, 1, 0.32, 1);
}

.hamburger-menu:after {
	content: "";
	position: absolute;
	left: 0;
	top: $bar-spacing;
	background: color(White);
	transition: top 300ms 300ms cubic-bezier(0.23, 1, 0.32, 1), transform 300ms cubic-bezier(0.23, 1, 0.32, 1);
}
.hamburger-menu {
	&.black {
		&::after {
			background: color(WhiteSecond);
		}
		&::before {
			background: color(WhiteSecond);
		}
	}
}

.hamburger-menu.animate:after {
	top: 0;
	transform: rotate(45deg);
	transition: top 300ms cubic-bezier(0.23, 1, 0.32, 1), transform 300ms 300ms cubic-bezier(0.23, 1, 0.32, 1);;
}

.hamburger-menu.animate:before {
	bottom: 0;
	transform: rotate(-45deg);
	transition: bottom 300ms cubic-bezier(0.23, 1, 0.32, 1), transform 300ms 300ms cubic-bezier(0.23, 1, 0.32, 1);;
}
</style>

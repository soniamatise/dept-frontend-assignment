<template>
	<header id="header" class="header">
		<div class="row center small-full medium-full large-24">
			<div class="column">
				<nav class="main-nav">
					<ul class="main-nav__list">
						<li class="main-nav__item">
							<nuxt-link to="/" class="main-nav__link">
								<span class="main-nav__text"><h1>Dept</h1></span>
							</nuxt-link>
						</li>
						<li class="main-nav__item main-nav__item--normal">
							<nuxt-link to="/work" class="main-nav__link">
								<span class="main-nav__text">Work</span>
							</nuxt-link>
						</li>
					
						<li class="main-nav__item main-nav__item--menubtn">
							<a class="button-container yellow cta-to-menu" @click="toggleMenu()">
								<p>MENU</p>
							</a>
						</li>
					</ul>
				</nav>
			</div>
		</div>
		<section :class="['menu__overlay', { 'active': showMenu }]">
			<div class="menu-wrapper" @click="toggleMenu()">
				<div class="hamburger-menu black animate" />
			</div>
			<div class="menu__inner menu__inner--navigation">
				<h4 @click="toggleMenu()">
					<nuxt-link to="/">Home</nuxt-link>
				</h4>
				<h4 @click="toggleMenu()">
					<nuxt-link to="/work">WORK</nuxt-link>
				</h4>
			</div>
		</section>
	</header>
</template>
<script>
export default {
	data() {
		return {
			showMenu: false
		};
	},
	// head () {
	//     return {
	//         bodyAttrs: {
	//             class: this.showMenu ? 'no-scroll-body' : '',
	//         }
	//     }
	// },
	methods: {
		toggleMenu: function () {
			this.showMenu = !this.showMenu;
		}
	}
};
</script>

<style lang="scss">
@import '~tools';

.header {
	padding: 3rem 0 1rem;
	background-color: color(Yellow);
	position: fixed;
	width: 100%;
	z-index: 2;
	height: 8rem;
	left: 0;
	top: 0;
	.main-nav {
		@media #{$medium-down} {
			margin: 0 25px;
		}
		&__list {
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			align-items: center;
		}
		&__item {
			cursor: pointer;
				@media #{$small-only} {
					width: 100%;
					// text-align: center;
				}
			&--normal {
				@media #{$small-only} {
					display: none;
				}
			}
			&--menubtn {
				display: none;
				position: relative;
				.cta-to-menu {
					position: absolute;
					transform: translate(0, -50%);
					right: 0;
					top: 50%;
					z-index: 1;
					padding: 10px;
					&:hover {
						animation: none;
					}
				}
				@media #{$small-only} {
					display: block;
				}
			}
		}
		&__text {
			position: relative;
			z-index: 1;
			@media #{$small-only} {
				h1 {font-size: 30px;}
			}
			&::after {
				content: '';
				position: absolute;
				left: 0;
				bottom: -2px;
				height: 1rem;
				width: 100%;
				background-color: color(Black);
				transition: height 200ms ease, background-color 600ms ease;
				z-index: -1;
			}
		}
		&__link {
			color: white;
			text-transform: uppercase;

			&:hover {
				.main-nav__text {
					&::after {
						height: 0rem;
					}
				}
			}
			&.nuxt-link-exact-active {
				.main-nav__text {
					color: color(White);
					&::after {
						height: 0rem;
					}
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
		z-index: 2;
		background-color: color(Yellow);
		color: color(Black);
		width: 100%;
		height: 100vh;
		justify-content: space-evenly;
		padding: 0 25px;
		transition: clip-path 0.5s ease-in-out, width 1s ease 1s;
		-webkit-clip-path: polygon(100% 0, 100% 0, 100% 100%, 100% 100%);
		clip-path: polygon(100% 0, 100% 0, 100% 100%, 100% 100%);

		display: none;
		@media #{$medium-down} {
			display: flex;
			flex-direction: column;
		}
		a {
			span.special-snowflake {
				color: color(Black);
				&::after { background-color: color(Red); }
			}
		}
		&.active {
			-webkit-clip-path: polygon(0 0, 100% 0%, 100% 100%, 0 100%);
			clip-path: polygon(0 0, 100% 0%, 100% 100%, 0 100%);
		}
	}
	&__inner {
		width: 100%;
		text-align: left;
		h4 { color: color(Black); }
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


$bar-width: 40px;
$bar-height: 5px;
$bar-spacing: 10px;

.menu-wrapper {
	position: fixed;
	top: 40px;
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
			background: color(Black);
		}
		&::before {
			background: color(Black);
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

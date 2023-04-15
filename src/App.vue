<template>
	<div class="app-container">
		<dv class="nav-bar">
			<header>snap</header>
			<!-- Decktop nav Sections -->
			<nav class="desktop-nav" v-if="isLargeScreen">
				<DesktopNav />
			</nav>

			<!-- Mobile nav Section -->
			<div class="mobile-nav" v-if="!isLargeScreen">
				<img
					src="./assets/images/svgs/icon-menu.svg"
					alt=""
					@click="open = true"
				/>
			</div>
			<Teleport to="body">
				<div class="navigation" v-if="open">
					<MobileNav @close-nav="open = false" />
				</div>
			</Teleport>
		</dv>
		<div class="main-section">
			<main class="main-content">
				<div class="hero-section">
					<div class="hero-image">
						<img
							:src="`/src/assets/images/pictures/image-hero-${
								isLargeScreen ? 'desktop' : 'mobile'
							}.png`"
							alt=""
						/>
					</div>

					<div class="hero-content">
						<h2 class="hero-header">Make remote work</h2>
						<p class="hero-snippet">
							Get your team in sync, no matter your location. Streamline
							processes, create team rituals, and watch productivity soar.
						</p>
						<button class="hero-cta">Learn more</button>

						<div class="footer-section">
							<Footer />
						</div>
					</div>
				</div>
			</main>
		</div>
	</div>
</template>

<script setup>
	import { ref } from "vue";
	import MobileNav from "./components/MobileNav.vue";
	import Footer from "./components/Footer.vue";
	import DesktopNav from "./components/DesktopNav.vue";
	import { useMediaQuery } from "@vueuse/core";

	const isLargeScreen = useMediaQuery("(min-width: 375px)");

	const open = ref(false);
</script>

<style lang="scss" scoped>
	@import "@/assets/base";

	.app-container {
		background-color: $almost-white;
	}

	// Desktop Navbar
	.desktop-nav {
		flex-grow: 1;
	}

	// Mobile Navbar
	.nav-bar {
		display: flex;
		justify-content: space-between;
		padding: 1rem;
		align-items: center;

		header {
			font-size: 2rem;
			font-weight: 700;
		}
	}

	// Teleported Navbar for mobile
	.navigation {
		position: absolute;
		top: 0;
		right: 0;
		z-index: 999;
		background-color: $almost-white;
		height: 100%;
		width: 65%;
		padding: 1rem 1rem 0 1rem;
	}

	// Hero Section
	.hero-section {
		color: $almost-black;

		.hero-image {
			height: 100%;

			img {
				object-fit: fill;
				width: 100%;
				height: 100%;
			}
		}

		.hero-content {
			display: grid;
			justify-content: center;

			.hero-header {
				text-align: center;
				font-size: 2rem;
				margin: 1rem 0 0 0;
			}

			.hero-snippet {
				text-align: center;
				font-size: 1rem;
				padding: 0 0.5rem;
				color: $medium-gray;
			}

			.hero-cta {
				padding: 1rem 0rem;
				width: 9rem;
				justify-self: center;
				border-radius: 1rem;
				background-color: hsl(0, 0%, 8%);
				color: hsl(0, 0%, 98%);
				font-weight: 700;
				font-size: 1rem;
			}

			.footer-section {
				margin-top: 2rem;
			}
		}
	}

	// Footer Section

	@media screen and (min-width: 375px) {
		.main-section {
			margin-top: 4rem;
		}
		.hero-section {
			display: flex;
			flex-direction: row-reverse;
			padding: 0 9rem;
			gap: 7rem;

			.hero-image {
				flex-grow: 1;
			}

			.hero-content {
				display: flex;
				flex-direction: column;
				justify-content: start;
				padding-top: 5rem;
				flex-grow: 1;

				.hero-header {
					text-align: left;
					font-size: 4rem;
				}

				.hero-snippet {
					text-align: left;
					padding: 0;
					margin: 3rem 0;
				}

				.footer-section {
					margin-top: 3rem;
				}
			}
		}
	}
</style>

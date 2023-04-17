<template>
	<div class="nav-container">
		<div class="left">
			<div class="left-item">
				<a href="#" class="link-item" @click="toggleFeatures = !toggleFeatures"
					><span>Features</span
					><img :src="toggleFeatures ? arrowUp : arrowDown" alt=""
				/></a>
				<div class="feature-dropdown" v-show="toggleFeatures">
					<a href="#" class="feature-item"
						><img src="@/assets/images/svgs/icon-todo.svg" alt="" /><span
							>Todo list</span
						>
					</a>
					<a href="#" class="feature-item"
						><img src="@/assets/images/svgs/icon-calendar.svg" alt="" /><span
							>Calender</span
						>
					</a>
					<a href="#" class="feature-item"
						><img src="@/assets/images/svgs/icon-reminders.svg" alt="" /><span
							>Reminders</span
						>
					</a>
					<a href="#" class="feature-item"
						><img src="@/assets/images/svgs/icon-planning.svg" alt="" /><span
							>Planning</span
						>
					</a>
				</div>
			</div>
			<div class="left-item">
				<a href="#" class="link-item" @click="toggleCompany = !toggleCompany"
					><span>Company</span
					><img :src="toggleCompany ? arrowUp : arrowDown" alt=""
				/></a>
				<div class="company-dropdown" v-show="toggleCompany">
					<a href="#" class="company-link-item"> History </a>
					<a href="#" class="company-link-item"> Our Team </a>
					<a href="#" class="company-link-item"> Blog </a>
				</div>
			</div>
			<div class="left-item">
				<a href="#" class="link-item"><span>Careers</span></a>
			</div>
			<div class="left-item">
				<a href="#" class="link-item"><span>About</span></a>
			</div>
		</div>
		<div class="right">
			<div class="right-item">
				<button class="right-btn">Login</button>
			</div>
			<div class="right-item">
				<button class="right-btn">Register</button>
			</div>
		</div>
	</div>
</template>

<script setup>
	import { ref } from "vue";
	import arrowDown from "@/assets/images/svgs/icon-arrow-down.svg";
	import arrowUp from "@/assets/images/svgs/icon-arrow-up.svg";

	const toggleFeatures = ref(false);

	const toggleCompany = ref(false);
</script>

<style lang="scss" scoped>
	@import "../assets/base";
	.nav-container {
		position: relative;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding-left: 2rem;

		// Left side
		.left {
			display: flex;
			gap: 1rem;

			.left-item {
				position: relative;

				.link-item {
					display: flex;
					justify-content: center;
					align-items: center;
					color: $medium-gray;
					font-size: 1rem;
					text-decoration: none;
					font-weight: 700;

					img {
						margin-left: 0.5rem;
					}
				}

				.link-item:hover {
					color: $almost-black;
				}
			}
		}

		// Right side
		.right {
			display: flex;

			.right-item {
				.right-btn {
					appearance: none;
					background-color: $almost-white;
					box-shadow: none;
					border: none;
					width: 7rem;
					font-size: 1rem;
					color: $medium-gray;
					padding: 1rem;
					cursor: pointer;
					font-weight: 700;
				}

				.right-btn:hover {
					color: $almost-black;
				}
			}
			.right-item:nth-child(2) {
				button {
					border: 1px solid $medium-gray;
					border-radius: 1rem;
				}

				button:hover {
					border: 1px solid $almost-black;
				}
			}
		}
	}

	// Dropdown for the feature section
	.feature-dropdown {
		position: absolute;
		display: grid;
		grid-template-columns: 1fr;
		gap: 1rem;
		background-color: $almost-white;
		box-shadow: 1px 0 12px -4px $almost-black;
		border-radius: 1rem;
		padding: 2rem 1rem;
		font-weight: 700;
		right: 0;
		width: 9rem;
		margin-top: 1rem;

		a {
			display: grid;
			text-decoration: none;
			justify-content: space-around;
			grid-template-columns: 1fr 3fr;
			color: $medium-gray;
		}
	}

	// Company dropdown
	.company-dropdown {
		position: absolute;
		display: grid;
		gap: 1rem;
		margin-top: 1rem;
		background-color: $almost-white;
		padding: 2rem 1rem;
		border-radius: 0.5rem;
		box-shadow: 1px 0 12px -4px $almost-black;
		width: 7rem;
		left: 0;
		font-weight: 700;

		a {
			display: grid;
			text-decoration: none;
			justify-content: space-around;
			grid-template-columns: 1fr 3fr;
			color: $medium-gray;
		}
	}
</style>

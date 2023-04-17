<template>
	<div class="mobile-nav">
		<div class="close-btn">
			<img
				src="@/assets/images/svgs/icon-close-menu.svg"
				alt=""
				@click="$emit('closeNav')"
			/>
		</div>
		<div class="nav-content">
			<div class="nav-item dropdown">
				<div class="dropdown-label">
					<a href="#" @click="openFeature = !openFeature"
						>Features <img :src="openFeature ? arrowUp : arrowDown" alt=""
					/></a>
				</div>
				<DropDown v-show="openFeature" :dropItems="[...featureLinks]" />
			</div>
		</div>
		<div class="nav-content">
			<div class="nav-item dropdown">
				<div class="dropdown-label">
					<a href="#" @click="openCompany = !openCompany"
						>Company<img :src="openCompany ? arrowUp : arrowDown" alt=""
					/></a>
				</div>
				<div class="company-dropdown" v-show="openCompany">
					<div class="dropitem">History</div>
					<div class="dropitem">Our Team</div>
					<div class="dropitem">Blog</div>
				</div>
			</div>
		</div>
		<div class="nav-content">
			<div class="nav-item dropdown">
				<div class="dropdown-label">
					<a href="#">Careers</a>
				</div>
			</div>
		</div>
		<div class="nav-content">
			<div class="nav-item dropdown">
				<div class="dropdown-label">
					<a href="#">About</a>
				</div>
			</div>
		</div>

		<div class="login-register">
			<button class="login lr-item">
				<a href="#">Login</a>
			</button>
			<button class="register lr-item">
				<a href="#">Register</a>
			</button>
		</div>
	</div>
</template>

<script setup>
	import { ref } from "vue";
	import DropDown from "./DropDown.vue";
	import arrowDown from "@/assets/images/svgs/icon-arrow-down.svg";
	import arrowUp from "@/assets/images/svgs/icon-arrow-up.svg";
	import TodoIcon from "@/assets/images/svgs/icon-todo.svg";
	import CalenderIcon from "@/assets/images/svgs/icon-calendar.svg";
	import RemindersIcon from "@/assets/images/svgs/icon-reminders.svg";
	import PlanningIcon from "@/assets/images/svgs/icon-planning.svg";

	const openFeature = ref(false);

	const openCompany = ref(false);

	const featureLinks = ref([
		{
			label: "Todo List",
			src: TodoIcon,
		},
		{
			label: "Calendar",
			src: CalenderIcon,
		},
		{
			label: "Reminders",
			src: RemindersIcon,
		},
		{
			label: "Planning",
			src: PlanningIcon,
		},
	]);
</script>

<style lang="scss" scoped>
	@import "../assets/base";
	.mobile-nav {
		color: $medium-gray;
		font-weight: 700;

		.close-btn {
			display: flex;
			justify-content: end;
			margin-bottom: 2rem;
		}

		// Nav Content Section
		.nav-content {
			.dropdown-label {
				margin: 1rem auto;

				a {
					text-decoration: none;
					color: inherit;
					display: flex;
					align-items: center;

					img {
						margin-left: 0.2rem;
					}
				}
			}
		}

		.company-dropdown {
			padding: 0 2rem;

			.dropitem {
				margin: 1rem 0;
			}
		}
	}

	// Login and Sign-up section
	.login-register {
		display: grid;
		justify-content: center;
		margin-top: 2rem;

		.lr-item {
			appearance: none;
			border: none;
			padding: 1rem;
			background-color: $almost-white;

			a {
				text-decoration: none;
				font-weight: 700;
				color: $medium-gray;
			}
		}

		.register {
			a {
				border: $almost-black solid 1px;
				border-radius: 1rem;
				padding: 1rem 4rem;
			}
		}
	}
</style>

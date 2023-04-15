<template>
	<div class="dropdown">
		<div v-for="{ label, src } in dropItems">
			<div class="drop-item">
				<img :src="src" alt="" />
				<span>{{ label }}</span>
			</div>
		</div>
	</div>
</template>

<script setup>
	defineProps(["dropItems"]);
</script>

<style lang="scss" scoped>
	.dropdown {
		padding-left: 2rem;

		.drop-item {
			margin-bottom: 1rem;

			img {
				margin-right: 0.5rem;
			}
		}
	}
</style>

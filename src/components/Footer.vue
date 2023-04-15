<template>
	<div class="footer-container">
		<div class="footer-item">
			<img src="../assets/images/svgs/client-databiz.svg" alt="" />
		</div>
		<div class="footer-item">
			<img src="../assets/images/svgs/client-audiophile.svg" alt="" />
		</div>
		<div class="footer-item">
			<img src="../assets/images/svgs/client-meet.svg" alt="" />
		</div>
		<div class="footer-item">
			<img src="../assets/images/svgs/client-maker.svg" alt="" />
		</div>
	</div>
</template>

<script setup></script>

<style lang="scss" scoped>
	.footer-container {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr;
		gap: 2rem;
		justify-content: space-around;
		align-items: center;
		padding: 0 1rem;

		.footer-item {
			height: 2rem;

			img {
				object-fit: contain;
				width: 100%;
				height: 100%;
			}
		}
	}
</style>

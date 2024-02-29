<script lang="ts">
	import Accordion from '$lib/components/Accordion.svelte';
</script>

<div class="container">
	<div class="header-background"></div>
	<Accordion />
	<div class="attribution">
		Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
			>Frontend Mentor</a
		>. Coded by <a href="/">Your Name Here</a>.
	</div>
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100vh;
	}

	.header-background {
		background-image: url('/assets/images/background-pattern-mobile.svg');
		background-size: cover;
		background-position: center;
		height: 250px;
		width: 100%;
		position: absolute;
		top: 0;
	}
</style>

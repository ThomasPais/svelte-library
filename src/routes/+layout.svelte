<script lang="ts">
	// Global Styles
	import '../app.css';

	// Layout
	import { Header } from '$lib/layout/header';
	import { Footer } from '$lib/layout/footer';
</script>

<div class="wrapper">
	<Header />
	<main>
		<slot />
	</main>
	<Footer />
</div>

<style>
	.wrapper {
		display: grid;
		grid-template-areas: 'header' 'main' 'footer';
		grid-template-rows: 72px 1fr 128px;
		height: 100%;
	}
</style>

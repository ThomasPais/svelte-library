<script lang="ts">
	// Global Styles
	import '../app.css';

	// Layout
	import { Header } from '$lib/layout/header';
	import { Footer } from '$lib/layout/footer';
</script>

<Header />
<main>
	<slot />
</main>
<Footer />

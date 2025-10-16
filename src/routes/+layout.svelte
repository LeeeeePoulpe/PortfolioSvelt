<script lang="ts">
	import '../app.css';
	import Navigation from '$lib/components/navigation.svelte';
	import ThemeProvider from '$lib/components/theme-provider.svelte';
	// import Analytics from '$lib/components/analytics.svelte';

	let { children } = $props();
</script>

<!-- 
Structure cible finale (à activer après création de Analytics) :
<ThemeProvider defaultTheme="system" storageKey="portfolio-theme">
	<Navigation />
	{@render children()}
	<Analytics />
</ThemeProvider>
-->

<ThemeProvider defaultTheme="system" storageKey="portfolio-theme">
	<Navigation />
	<div class="min-h-screen">
		{@render children()}
	</div>
	<!-- <Analytics /> -->
</ThemeProvider>

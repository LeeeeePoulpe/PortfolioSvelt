<script lang="ts">
	import '../app.css';
	import Navigation from '$lib/components/navigation.svelte';
	import ThemeProvider from '$lib/components/theme-provider.svelte';
	import Analytics from '$lib/components/analytics.svelte';

	let { children } = $props();
</script>

<ThemeProvider defaultTheme="system" storageKey="portfolio-theme">
	<Navigation />
	<div class="min-h-screen">
		{@render children()}
	</div>
	<Analytics />
</ThemeProvider>

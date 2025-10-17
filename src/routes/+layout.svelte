<script lang="ts">
	import '../app.css';
	import Navigation from '$lib/components/navigation.svelte';
	import ThemeProvider from '$lib/components/theme-provider.svelte';
	import Analytics from '$lib/components/analytics.svelte';

	let { children } = $props();
</script>

<ThemeProvider defaultTheme="system" storageKey="portfolio-theme">
	<div class="pointer-events-none fixed inset-0 -z-10 overflow-hidden">
		<div
			class="absolute left-1/2 top-1/2 h-[300px] w-[300px] -translate-x-1/2 -translate-y-1/2 animate-pulse rounded-full bg-purple-400/30 blur-[120px] md:h-[500px] md:w-[500px] lg:h-[500px] lg:w-[500px] 2xl:h-[800px] 2xl:w-[800px]"
		></div>
	</div>
	<Navigation />
	<div class="min-h-screen">
		{@render children()}
	</div>
	<Analytics />
</ThemeProvider>

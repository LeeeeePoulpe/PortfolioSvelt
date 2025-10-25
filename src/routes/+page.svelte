<script lang="ts">
	import HeroSection from '$lib/components/page/hero-section.svelte';
	import ProjectSection from '$lib/components/page/project-section.svelte';
	import AboutSection from '$lib/components/page/about-section.svelte';
	import ScrollIndicator from '$lib/components/page/scroll-indicator.svelte';
</script>

<main class="min-h-screen pt-16">
	<ScrollIndicator />
	<HeroSection />
	<ProjectSection />
	<AboutSection />
</main>

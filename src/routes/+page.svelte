<script lang="ts">
	import HeroSection from '$lib/components/page/hero-section.svelte';
	import ProjectSection from '$lib/components/page/project-section.svelte';
	import AboutSection from '$lib/components/page/about-section.svelte';
	import ScrollIndicator from '$lib/components/page/scroll-indicator.svelte';
</script>

<svelte:head>
	<title>Hugo Föllmi - Portfolio</title>
	<meta
		name="description"
		content="Portfolio professionnel de Hugo Föllmi - Développeur web et mobile passionné"
	/>
</svelte:head>

<main class="min-h-screen pt-16">
	<ScrollIndicator />
	<HeroSection />
	<ProjectSection />
	<AboutSection />
</main>

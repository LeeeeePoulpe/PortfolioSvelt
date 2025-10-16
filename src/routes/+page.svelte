<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import { ArrowRight, Github, Linkedin, Mail } from '@lucide/svelte';
	import { fade, fly } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	
	let isVisible = $state(false);
	
	$effect(() => {
		isVisible = true;
	});
</script>

<main class="min-h-screen pt-16">
	<!-- Hero Section -->
	<section class="relative min-h-[calc(100vh-4rem)] flex items-center justify-center px-4 sm:px-6 lg:px-8">
		<div class="max-w-4xl mx-auto text-center">
			{#if isVisible}
				<div
					in:fly={{ y: 20, duration: 600, easing: quintOut }}
				>
					<h1 class="font-display text-5xl sm:text-6xl lg:text-7xl font-bold text-foreground mb-6 text-balance">
						Hugo Föllmi
					</h1>
					<p class="text-xl sm:text-2xl text-muted-foreground mb-8 text-balance">
						Développeur passionné par la création d'expériences numériques innovantes
					</p>
				</div>

				<div
					in:fly={{ y: 20, duration: 600, delay: 200, easing: quintOut }}
					class="flex flex-col sm:flex-row items-center justify-center gap-4 mb-12"
				>
					<Button size="lg" class="group">
						<a href="/projects" class="flex items-center">
							Voir mes projets
							<ArrowRight class="ml-2 h-4 w-4 transition-transform group-hover:translate-x-1" />
						</a>
					</Button>
					<Button variant="outline" size="lg">
						<a href="/contact">Me contacter</a>
					</Button>
				</div>

				<div
					in:fade={{ duration: 600, delay: 400 }}
					class="flex items-center justify-center gap-6"
				>
					<a
						href="https://github.com/hugofollmi"
						target="_blank"
						rel="noopener noreferrer"
						class="text-muted-foreground hover:text-secondary transition-colors"
						aria-label="GitHub"
					>
						<Github size={24} />
					</a>
					<a
						href="https://linkedin.com/in/hugofollmi"
						target="_blank"
						rel="noopener noreferrer"
						class="text-muted-foreground hover:text-secondary transition-colors"
						aria-label="LinkedIn"
					>
						<Linkedin size={24} />
					</a>
					<a
						href="mailto:contact@hugofollmi.com"
						class="text-muted-foreground hover:text-secondary transition-colors"
						aria-label="Email"
					>
						<Mail size={24} />
					</a>
				</div>
			{/if}
		</div>

		<!-- Animated background element -->
		<div class="absolute inset-0 -z-10 overflow-hidden">
			<div
				class="absolute top-1/4 right-1/4 w-96 h-96 bg-secondary/10 rounded-full blur-3xl animate-pulse-slow"
			></div>
			<div
				class="absolute bottom-1/4 left-1/4 w-96 h-96 bg-accent/10 rounded-full blur-3xl animate-pulse-slow"
				style="animation-delay: 4s;"
			></div>
		</div>
	</section>

	<!-- Quick About Section -->
	<section class="py-20 px-4 sm:px-6 lg:px-8 bg-muted/30">
		<div class="max-w-4xl mx-auto">
			<div>
				<h2 class="font-display text-3xl sm:text-4xl font-bold text-foreground mb-6 text-center">
					À propos
				</h2>
				<p class="text-lg text-muted-foreground text-center leading-relaxed mb-8">
					Étudiant passionné par le développement web et mobile, je crée des applications modernes et performantes.
					Spécialisé en Java, Python, Symfony et bien plus encore.
				</p>
				<div class="text-center">
					<Button variant="outline">
						<a href="/about">En savoir plus</a>
					</Button>
				</div>
			</div>
		</div>
	</section>
</main>

<style>
	@keyframes pulse-slow {
		0%, 100% {
			transform: scale(1);
			opacity: 0.3;
		}
		50% {
			transform: scale(1.2);
			opacity: 0.5;
		}
	}

	.animate-pulse-slow {
		animation: pulse-slow 8s ease-in-out infinite;
	}
</style>

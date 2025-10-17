<script lang="ts">
	import HeroSection from '$lib/components/page/hero-section.svelte';
	import Button from '$lib/components/ui/button/button.svelte';
	import { Motion } from 'svelte-motion';
</script>

<main class="min-h-screen pt-16">
	<section
		class="relative flex min-h-[calc(100vh-4rem)] items-center justify-center px-4 sm:px-6 lg:px-8"
	>
        <HeroSection />
	</section>

	<!-- Quick About Section -->
	<section class="bg-muted/30 px-4 py-20 sm:px-6 lg:px-8">
		<div class="mx-auto max-w-4xl">
			<Motion
				let:motion
				initial={{ opacity: 0, y: 30 }}
				whileInView={{ opacity: 1, y: 0 }}
				viewport={{ once: true }}
				transition={{ duration: 0.8 }}
			>
				<div use:motion>
					<h2 class="font-display mb-6 text-center text-3xl font-bold text-foreground sm:text-4xl">
						À propos
					</h2>
					<p class="mb-8 text-center text-lg leading-relaxed text-muted-foreground">
						Étudiant passionné par le développement web et mobile, je crée des applications modernes
						et performantes. Spécialisé en Java, Python, Symfony et bien plus encore.
					</p>
					<div class="text-center">
						<Button variant="outline">
							<a href="/about">En savoir plus</a>
						</Button>
					</div>
				</div>
			</Motion>
		</div>
	</section>
</main>

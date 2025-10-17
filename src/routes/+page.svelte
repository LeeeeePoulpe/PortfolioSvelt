<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import { ArrowRight, Github, Linkedin, Mail } from '@lucide/svelte';
	import { Motion } from 'svelte-motion';
</script>

<main class="min-h-screen pt-16">
	<!-- Hero Section -->
	<section
		class="relative flex min-h-[calc(100vh-4rem)] items-center justify-center px-4 sm:px-6 lg:px-8"
	>
		<div class="mx-auto max-w-4xl text-center">
			<!-- Titre et description -->
			<Motion
				let:motion
				initial={{ opacity: 0, y: 20 }}
				animate={{ opacity: 1, y: 0 }}
				transition={{ duration: 0.6 }}
			>
				<div use:motion>
					<h1
						class="font-display mb-6 text-5xl font-bold text-balance text-foreground sm:text-6xl lg:text-7xl"
					>
						Hugo Föllmi
					</h1>
					<p class="mb-8 text-xl text-balance text-muted-foreground sm:text-2xl">
						Développeur passionné par la création d'expériences numériques innovantes
					</p>
				</div>
			</Motion>

			<!-- Boutons CTA -->
			<Motion
				let:motion
				initial={{ opacity: 0, y: 20 }}
				animate={{ opacity: 1, y: 0 }}
				transition={{ duration: 0.6, delay: 0.2 }}
			>
				<div
					use:motion
					class="mb-12 flex flex-col items-center justify-center gap-4 sm:flex-row"
				>
					<Motion let:motion whileHover={{ scale: 1.05 }} whileTap={{ scale: 0.95 }}>
						<div use:motion>
							<Button size="lg" class="group">
								<a href="/projects" class="flex items-center">
									Voir mes projets
									<ArrowRight
										class="ml-2 h-4 w-4 transition-transform group-hover:translate-x-1"
									/>
								</a>
							</Button>
						</div>
					</Motion>

					<Motion let:motion whileHover={{ scale: 1.05 }} whileTap={{ scale: 0.95 }}>
						<div use:motion>
							<Button variant="outline" size="lg">
								<a href="/contact">Me contacter</a>
							</Button>
						</div>
					</Motion>
				</div>
			</Motion>

			<!-- Liens sociaux -->
			<Motion
				let:motion
				initial={{ opacity: 0 }}
				animate={{ opacity: 1 }}
				transition={{ duration: 0.6, delay: 0.4 }}
			>
				<div use:motion class="flex items-center justify-center gap-6">
					<a
						href="https://github.com/LeeeeePoulpe"
						target="_blank"
						rel="noopener noreferrer"
						class="text-muted-foreground transition-colors hover:text-secondary"
						aria-label="GitHub"
					>
						<Github size={24} />
					</a>
					<a
						href="https://www.linkedin.com/in/hugo-follmi-71a971214/"
						target="_blank"
						rel="noopener noreferrer"
						class="text-muted-foreground transition-colors hover:text-secondary"
						aria-label="LinkedIn"
					>
						<Linkedin size={24} />
					</a>
					<a
						href="mailto:contact@hugofollmi@gmail.com"
						class="text-muted-foreground transition-colors hover:text-secondary"
						aria-label="Email"
					>
						<Mail size={24} />
					</a>
				</div>
			</Motion>
		</div>

		<!-- Animated background element -->
		<div class="absolute inset-0 -z-10 overflow-hidden">
			<Motion
				let:motion
				animate={{ scale: [1, 1.2, 1], opacity: [0.3, 0.5, 0.3] }}
				transition={{ duration: 8, repeat: Infinity, ease: 'easeInOut' }}
			>
				<div
					use:motion
					class="absolute top-1/4 right-1/4 h-96 w-96 rounded-full bg-secondary/10 blur-3xl"
				></div>
			</Motion>
			<Motion
				let:motion
				animate={{ scale: [1.2, 1, 1.2], opacity: [0.5, 0.3, 0.5] }}
				transition={{ duration: 8, repeat: Infinity, ease: 'easeInOut' }}
			>
				<div
					use:motion
					class="absolute bottom-1/4 left-1/4 h-96 w-96 rounded-full bg-accent/10 blur-3xl"
				></div>
			</Motion>
		</div>
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
						Étudiant passionné par le développement web et mobile, je crée des applications
						modernes et performantes. Spécialisé en Java, Python, Symfony et bien plus encore.
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

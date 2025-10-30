<script lang="ts">
	import { Motion } from 'svelte-motion';
	import Button from '$lib/components/ui/button/button.svelte';
	import { ArrowRight, Github, Linkedin, Mail } from '@lucide/svelte';
</script>

<section
	class="relative flex min-h-[calc(100vh-4rem)] items-center justify-center px-4 sm:px-6 lg:px-8"
>
	<div class="mx-auto max-w-4xl text-center">
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
			<div use:motion class="mb-12 flex flex-col items-center justify-center gap-4 sm:flex-row">
				<Motion let:motion whileHover={{ scale: 1.05 }} whileTap={{ scale: 0.95 }}>
					<div use:motion>
						<Button size="lg" class="group" href="/projects">
							Voir mes projets
							<ArrowRight class="ml-2 h-4 w-4" />
						</Button>
					</div>
				</Motion>

				<Motion let:motion whileHover={{ scale: 1.05 }} whileTap={{ scale: 0.95 }}>
					<div use:motion>
						<Button variant="outline" size="lg" href="/contact">Me contacter</Button>
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
					class="text-foreground transition-colors hover:text-secondary"
					aria-label="GitHub"
				>
					<Github size={24} />
				</a>
				<a
					href="https://www.linkedin.com/in/hugo-follmi-71a971214/"
					target="_blank"
					rel="noopener noreferrer"
					class="text-foreground transition-colors hover:text-secondary"
					aria-label="LinkedIn"
				>
					<Linkedin size={24} />
				</a>
				<a
					href="mailto:contact@hugofollmi@gmail.com"
					class="text-foreground transition-colors hover:text-secondary"
					aria-label="Email"
				>
					<Mail size={24} />
				</a>
			</div>
		</Motion>
	</div>
</section>

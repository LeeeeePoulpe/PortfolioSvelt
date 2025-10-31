<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Sparkles } from '@lucide/svelte';
	import IconSvelte from '~icons/devicon/svelte';
	import IconMotion from '~icons/simple-icons/framer';
	import IconShadcn from '~icons/simple-icons/shadcnui';
	import IconTailwindcss from '~icons/devicon/tailwindcss';

	const techStack = [
		{
			name: 'SvelteKit',
			url: 'https://kit.svelte.dev',
			Icon: IconSvelte
		},
		{
			name: 'Svelte Motion',
			url: 'https://motion.svelte.dev',
			Icon: IconMotion
		},
		{
			name: 'Shadcn-Svelte',
			url: 'https://www.shadcn-svelte.com',
			Icon: IconShadcn
		},
		{
			name: 'Tailwind CSS',
			url: 'https://tailwindcss.com',
			Icon: IconTailwindcss
		}
	];
</script>

<footer class="relative mt-32 border-t border-border/50 backdrop-blur-sm">
	<div class="container mx-auto px-6 py-12">
		<Motion
			initial={{ opacity: 0, y: 20 }}
			whileInView={{ opacity: 1, y: 0 }}
			viewport={{ once: true }}
			transition={{ duration: 0.6 }}
			let:motion
		>
			<div use:motion class="flex flex-col items-center gap-8">
				<!-- Tech Stack Section -->
				<div class="flex flex-col items-center gap-4">
					<div class="flex items-center gap-2 text-sm text-muted-foreground">
						<Sparkles class="h-4 w-4 text-secondary" />
						<span>Construit avec</span>
					</div>
					<div class="flex items-center gap-6">
						{#each techStack as tech}
							<Motion whileHover={{ scale: 1.1 }} let:motion>
								<a
									use:motion
									href={tech.url}
									target="_blank"
									rel="noopener noreferrer"
									title={tech.name}
								>
									<tech.Icon class="h-6 w-6" />
								</a>
							</Motion>
						{/each}
					</div>
				</div>

				<!-- Learning Note -->
				<Motion
					initial={{ opacity: 0, y: 20 }}
					whileInView={{ opacity: 1, y: 0 }}
					viewport={{ once: true }}
					transition={{ duration: 0.6, delay: 0.3 }}
					let:motion
				>
					<div use:motion class="max-w-2xl text-center">
						<p class="text-sm leading-relaxed text-muted-foreground">
							Première expérience avec <span class="font-medium text-secondary">SvelteKit</span>.
							Découverte de ce framework moderne pour créer un portfolio performant et élégant.
						</p>
					</div>
				</Motion>

				<!-- Copyright -->
				<div class="text-xs text-muted-foreground/60">
					© {new Date().getFullYear()} Hugo Föllmi. Tous droits réservés.
				</div>
			</div>
		</Motion>
	</div>
</footer>

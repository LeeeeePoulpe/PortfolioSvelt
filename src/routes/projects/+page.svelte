<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardDescription, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { ExternalLink, Github } from '@lucide/svelte';
	import { Button } from '$lib/components/ui/button/index.js';

	const projects = [
		{
			title: 'Sciconf',
			description: 'Plateforme de gestion de conférences scientifiques développée avec Symfony',
			tags: ['Symfony', 'PHP', 'PostgreSQL'],
			year: '2023',
			links: {
				github: '#'
			}
		},
		{
			title: 'LudoLabo',
			description: 'Application de gestion de laboratoire de jeux vidéo',
			tags: ['Java', 'Android', 'SQLite'],
			year: '2024',
			links: {
				github: '#'
			}
		},
		{
			title: 'GameJam 2023',
			description: 'Jeu vidéo créé lors d\'une GameJam avec Unity',
			tags: ['Unity', 'C#', 'Game Design'],
			year: '2023',
			links: {
				demo: '#'
			}
		},
		{
			title: 'Arcsecond',
			description: 'Application mobile de visualisation astronomique',
			tags: ['React Native', 'TypeScript', 'API'],
			year: '2023',
			links: {
				github: '#'
			}
		},
		{
			title: 'Stage ErgoGames',
			description: 'Développement d\'outils ergonomiques pour jeux vidéo',
			tags: ['Python', 'Data Analysis', 'UX'],
			year: '2024',
			links: {
				demo: '#'
			}
		},
		{
			title: 'GameJam 2024',
			description: 'Nouveau projet de jeu créé en 48h',
			tags: ['Unity', 'C#', 'Multiplayer'],
			year: '2024',
			links: {
				demo: '#',
				github: '#'
			}
		}
	];
</script>

<main class="min-h-screen px-4 pt-32 pb-16 sm:px-6 lg:px-8">
	<div class="mx-auto max-w-5xl">
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6 }}
		>
			<div use:motion>
				<h1 class="font-display mb-4 text-4xl font-bold text-foreground sm:text-5xl">
					Mes projets
				</h1>
				<p class="mb-12 text-lg leading-relaxed text-muted-foreground">
					Une sélection de mes réalisations en développement web, mobile et jeux vidéo
				</p>
			</div>
		</Motion>

		<div class="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">
			{#each projects as project, index}
				<Motion
					let:motion
					initial={{ opacity: 0, y: 20 }}
					animate={{ opacity: 1, y: 0 }}
					transition={{ duration: 0.6, delay: 0.1 + index * 0.1 }}
				>
					<div use:motion>
						<Card class="flex h-full flex-col transition-all hover:-translate-y-1 hover:shadow-lg">
							<CardHeader>
								<div class="mb-2 flex items-start justify-between">
									<CardTitle class="font-display text-xl">{project.title}</CardTitle>
									<span class="text-sm text-muted-foreground">{project.year}</span>
								</div>
								<CardDescription class="leading-relaxed">
									{project.description}
								</CardDescription>
							</CardHeader>
							<CardContent class="flex flex-1 flex-col justify-between">
								<div class="mb-4 flex flex-wrap gap-2">
									{#each project.tags as tag}
										<Badge variant="secondary">
											{tag}
										</Badge>
									{/each}
								</div>
								<div class="flex gap-2">
									{#if project.links.github}
										<Button variant="outline" size="sm" href={project.links.github}>
											<Github class="mr-2 h-4 w-4" />
											Code
										</Button>
									{/if}
									{#if project.links.demo}
										<Button variant="outline" size="sm" href={project.links.demo}>
											<ExternalLink class="mr-2 h-4 w-4" />
											Demo
										</Button>
									{/if}
								</div>
							</CardContent>
						</Card>
					</div>
				</Motion>
			{/each}
		</div>
	</div>
</main>


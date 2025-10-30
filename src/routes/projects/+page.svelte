<script lang="ts">
	import { Motion } from 'svelte-motion';
	import {
		Card,
		CardContent,
		CardDescription,
		CardHeader,
		CardTitle
	} from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { ExternalLink, Github } from '@lucide/svelte';
	import { Button } from '$lib/components/ui/button/index.js';

	const projects = [
		{
			title: 'Alternance Enogrid',
			description:
				'Développement front-end sur Mon Energie Collective et EnoConso, plateformes de transition énergétique',
			tags: ['React', 'TypeScript', 'MongoDB', 'Neo4j'],
			year: '2025',
			page: '/projects/alternance-enogrid',
			links: {
				demo: 'https://monenergiecollective.fr/'
			}
		},
		{
			title: 'ErgoGames',
			description:
				'Développement du jeu "Au pas de course !" chez Sogilis pour enseigner les principes ergonomiques',
			tags: ['Vue.js', 'JavaScript', 'Vuetify', 'Figma'],
			year: '2024',
			page: '/projects/ergogames',
			links: {
				demo: 'https://www.ergogames.fr/',
				github: 'https://github.com/sogilis'
			}
		},
		{
			title: 'LudoLabo',
			description:
				'Application ludique pour réviser la physique-chimie en terminale avec système de classes',
			tags: ['Vue.js', 'Tailwind CSS', 'Unity', 'PrelineUI'],
			year: '2024',
			page: '/projects/ludolabo',
			links: {
				github: 'https://github.com/LudoLaboApp'
			}
		},
		{
			title: 'GameJam 2024',
			description: 'Nation Chase - Jeu multijoueur de loup touche-touche sur le thème des nations',
			tags: ['Python', 'PyGame', 'Multiplayer', 'Network'],
			year: '2024',
			page: '/projects/gamejam-2024',
			links: {
				github: 'https://github.com/sadspear/gamejam'
			}
		},
		{
			title: 'Carnet de Stage',
			description:
				"Réparation et amélioration de l'application Android et du site web du carnet de stage IUT2",
			tags: ['Android', 'Java', 'MySQL', 'Docker', 'Material Design 3'],
			year: '2024',
			page: '/projects/carnet-de-stage',
			links: {}
		},
		{
			title: 'GameJam 2023',
			description:
				'Time Striker - Jeu style Pokémon dans l\'IUT2 sur le thème "Le merveilleux monde de l\'IUT2"',
			tags: ['Python', 'PyGame', 'Game Design', 'Team Work'],
			year: '2023',
			page: '/projects/gamejam-2023',
			links: {
				github: 'https://github.com/sadspear/gamejam2023'
			}
		},
		{
			title: 'Sciconf',
			description: 'Application de gestion de conférences scientifiques avec Java, JavaFX et MySQL',
			tags: ['Java', 'JavaFX', 'MySQL', 'Desktop'],
			year: '2023',
			page: '/projects/sciconf',
			links: {}
		}
	];
</script>

<svelte:head>
	<title>Projets - Hugo Föllmi</title>
	<meta name="description" content="Découvrez mes projets en développement web, mobile et jeux vidéo" />
</svelte:head>

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
						<Card
							class="group flex h-full flex-col transition-all hover:-translate-y-1 hover:shadow-lg"
						>
							<CardHeader class="pb-3">
								<div class="mb-2 flex items-start justify-between">
									<CardTitle
										class="font-display text-xl transition-colors group-hover:text-primary"
									>
										{project.title}
									</CardTitle>
									<span class="text-sm text-muted-foreground">{project.year}</span>
								</div>
								<CardDescription class="text-sm leading-relaxed">
									{project.description}
								</CardDescription>
							</CardHeader>
							<CardContent class="flex flex-1 flex-col justify-between pt-0">
								<div class="mb-4 flex flex-wrap gap-2">
									{#each project.tags as tag}
										<Badge variant="secondary" class="text-xs">
											{tag}
										</Badge>
									{/each}
								</div>
								<div class="flex flex-col gap-2">
									{#if project.page}
										<Button variant="default" size="sm" href={project.page} class="w-full">
											<ExternalLink class="mr-2 h-4 w-4" />
											Voir le projet
										</Button>
									{/if}
									<div class="flex gap-2">
										{#if project.links.github}
											<Button
												variant="outline"
												size="sm"
												href={project.links.github}
												target="_blank"
												rel="noopener noreferrer"
												class="flex-1"
											>
												<Github class="mr-2 h-4 w-4" />
												Code
											</Button>
										{/if}
										{#if project.links.demo}
											<Button
												variant="outline"
												size="sm"
												href={project.links.demo}
												target="_blank"
												rel="noopener noreferrer"
												class="flex-1"
											>
												<ExternalLink class="mr-2 h-4 w-4" />
												Demo
											</Button>
										{/if}
									</div>
								</div>
							</CardContent>
						</Card>
					</div>
				</Motion>
			{/each}
		</div>
	</div>
</main>

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
	import { ExternalLink, Github, ArrowRight } from '@lucide/svelte';
	import { Button } from '$lib/components/ui/button/index.js';

	const featuredProjects = [
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
		}
	];
</script>

<section class="px-4 py-20 sm:px-6 lg:px-8">
	<div class="mx-auto max-w-5xl">
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			whileInView={{ opacity: 1, y: 0 }}
			viewport={{ once: true }}
			transition={{ duration: 0.6 }}
		>
			<div use:motion class="mb-12 text-center">
				<h2 class="font-display mb-4 text-3xl font-bold text-foreground sm:text-4xl">
					Projets récents
				</h2>
				<p class="text-lg text-muted-foreground">Découvrez mes dernières réalisations</p>
			</div>
		</Motion>

		<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
			{#each featuredProjects as project, index}
				<Motion
					let:motion
					initial={{ opacity: 0, y: 20 }}
					whileInView={{ opacity: 1, y: 0 }}
					viewport={{ once: true }}
					transition={{ duration: 0.6, delay: index * 0.1 }}
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
								<CardDescription class="leading-relaxed">
									{project.description}
								</CardDescription>
							</CardHeader>
							<CardContent class="flex flex-1 flex-col justify-between pt-0">
								<div class="mb-4 flex flex-wrap gap-2">
									{#each project.tags as tag}
										<Badge variant="secondary">
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

		<Motion
			let:motion
			initial={{ opacity: 0 }}
			whileInView={{ opacity: 1 }}
			viewport={{ once: true }}
			transition={{ duration: 0.6, delay: 0.3 }}
		>
			<div use:motion class="mt-12 text-center">
				<Button variant="outline" size="lg" href="/projects" class="group bg-transparent">
					Voir tous les projets
					<ArrowRight class="ml-2 h-4 w-4 transition-transform group-hover:translate-x-1" />
				</Button>
			</div>
		</Motion>
	</div>
</section>


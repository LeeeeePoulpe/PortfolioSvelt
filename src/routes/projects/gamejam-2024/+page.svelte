<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import { ExternalLink, Calendar, Users, Gamepad2, Network, Zap, ArrowLeft } from '@lucide/svelte';
	import { onMount } from 'svelte';
	
	onMount(() => {
		if (typeof document !== 'undefined') {
			document.title = 'GameJam 2024 - Hugo Föllmi';
		}
	});

	const technologies = [
		{ name: 'Python', color: '#3776AB', url: 'https://www.python.org/' },
		{ name: 'PyGame', color: '#FF6B6B', url: 'https://www.pygame.org/' }
	];

	const nations = [
		{ name: 'Jamaïque', ability: 'Bonus de vitesse', color: '#FFD700' },
		{ name: 'Nation Éclair', ability: 'Lancer un éclair pour ralentir', color: '#FF6B6B' },
		{ name: 'Autres nations', ability: 'Capacités uniques variées', color: '#4ECDC4' }
	];

	const teamRoles = [
		{
			role: 'Spécialiste réseau',
			description: 'Gestion de la communication entre joueurs',
			icon: Network
		},
		{
			role: 'Développeurs gameplay',
			description: 'Cartes, physique, menus, chronométrage, mécanique de changement de rôle',
			icon: Gamepad2
		}
	];

	const gameMechanics = [
		{
			title: 'Concept de base',
			description: 'Loup touche-touche (tag) multijoueur inspiré du Chase Tag'
		},
		{
			title: 'Objectif',
			description: 'Éviter d\'être le "loup" et minimiser son temps dans ce rôle'
		},
		{
			title: 'Capacités spéciales',
			description: 'Chaque nation a une capacité unique (vitesse, éclair, etc.)'
		},
		{
			title: 'Victoire',
			description: 'Le joueur avec le temps le plus court en tant que "loup" gagne'
		}
	];
</script>

<svelte:head>
	<title>GameJam 2024 - Nation Chase - Hugo Föllmi</title>
	<meta
		name="description"
		content="Développement du jeu multijoueur Nation Chase lors de la GameJam 2024 sur le thème 'L'affrontement pacifique entre les nations'."
	/>
</svelte:head>

<main class="min-h-screen pt-32 pb-16">
	<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8">
		<!-- Back Button -->
		<Motion
			let:motion
			initial={{ opacity: 0, x: -20 }}
			animate={{ opacity: 1, x: 0 }}
			transition={{ duration: 0.4 }}
		>
			<div use:motion class="mb-6">
				<Button variant="ghost" href="/projects" class="gap-2">
					<ArrowLeft class="h-4 w-4" />
					Retour aux projets
				</Button>
			</div>
		</Motion>

		<!-- Header Section -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6 }}
		>
			<div use:motion class="mb-12">
				<div class="flex flex-col items-start gap-8 lg:flex-row">
					<div class="flex-1">
						<h1 class="font-display mb-6 text-4xl font-bold text-foreground sm:text-5xl">
							GameJam 2024 - Nation Chase
						</h1>
						<p class="mb-6 text-lg leading-relaxed text-muted-foreground">
							Participation à la
							<a
								href="https://fr.wikipedia.org/wiki/Game_jam"
								target="_blank"
								class="text-primary hover:underline"
							>
								GameJam
							</a>
							2024 lors du BUT Informatique à l'IUT2 de Grenoble. Développement du jeu multijoueur
							<a
								href="https://github.com/sadspear/gamejam"
								target="_blank"
								class="text-primary hover:underline"
							>
								Nation Chase
							</a>
							sur le thème "L'affrontement pacifique entre les nations" en équipe de 5 étudiants.
						</p>
						<div class="mb-6 flex flex-wrap gap-2">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								3e année de BUT
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Users class="h-3 w-3" />
								Équipe de 5
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Network class="h-3 w-3" />
								Multijoueurs
							</Badge>
						</div>
					</div>
					<div class="flex w-full flex-col gap-4 lg:w-80">
						<a
							href="https://github.com/sadspear/gamejam"
							target="_blank"
							class="group rounded-lg border p-4 transition-all hover:shadow-lg"
						>
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 items-center justify-center rounded-lg bg-gradient-to-br from-red-500 to-blue-600"
								>
									<span class="text-lg font-bold text-white">NC</span>
								</div>
								<div>
									<h3 class="font-semibold">Nation Chase</h3>
									<p class="text-sm text-muted-foreground">Repository GitHub</p>
								</div>
								<ExternalLink
									class="ml-auto h-4 w-4 opacity-0 transition-opacity group-hover:opacity-100"
								/>
							</div>
						</a>
						<div class="rounded-lg border p-4">
							<div class="mb-3 flex items-center gap-3">
								<Zap class="h-8 w-8 text-yellow-500" />
								<div>
									<h3 class="font-semibold">GameJam 2024</h3>
									<p class="text-sm text-muted-foreground">Événement national</p>
								</div>
							</div>
							<p class="text-sm text-muted-foreground">
								Développement d'un jeu vidéo avec contraintes en une semaine.
							</p>
						</div>
					</div>
				</div>
			</div>
		</Motion>

		<!-- Contexte -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.2 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Contexte du projet</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div class="grid grid-cols-1 gap-8 lg:grid-cols-2">
							<div>
								<h3 class="mb-4 text-xl font-semibold">La GameJam 2024</h3>
								<p class="mb-4 leading-relaxed text-muted-foreground">
									Événement stimulant durant lequel des équipes d'étudiants doivent concevoir et
									développer un jeu vidéo en respectant des contraintes de temps et de thème. Notre
									équipe était composée de cinq étudiants.
								</p>
								<p class="leading-relaxed text-muted-foreground">
									Le thème imposé était "L'affrontement pacifique entre les nations", avec la
									particularité de devoir développer un jeu multijoueur en
									<a
										href="https://developer.mozilla.org/fr/docs/Glossary/Python"
										target="_blank"
										class="text-primary hover:underline"
									>
										Python
									</a>
									et
									<a
										href="https://www.pygame.org/"
										target="_blank"
										class="text-primary hover:underline"
									>
										PyGame
									</a>.
								</p>
							</div>
							<div>
								<h3 class="mb-4 text-xl font-semibold">Nation Chase</h3>
								<p class="leading-relaxed text-muted-foreground">
									Notre création baptisée "Nation Chase" est un jeu de loup touche-touche (tag)
									multijoueur, inspiré par les
									<a
										href="https://www.worldchasetag.com/"
										target="_blank"
										class="text-primary hover:underline"
									>
										championnats du monde de Chase Tag
									</a>. Chaque nation possède des capacités uniques pour dynamiser le gameplay.
								</p>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Concept du jeu -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.4 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Concept et mécaniques du jeu</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
							{#each gameMechanics as mechanic}
								<div class="rounded-lg border p-4 transition-shadow hover:shadow-md">
									<h4 class="mb-2 font-semibold">{mechanic.title}</h4>
									<p class="text-sm text-muted-foreground">{mechanic.description}</p>
								</div>
							{/each}
						</div>

						<div
							class="mt-6 rounded-lg bg-gradient-to-r from-blue-50 to-purple-50 p-4 dark:from-blue-500/10 dark:to-purple-500/10"
						>
							<h4 class="mb-3 font-semibold">Nations et capacités</h4>
							<div class="grid grid-cols-1 gap-4 md:grid-cols-3">
								{#each nations as nation}
									<div class="rounded-lg border p-3">
										<div class="mb-2 flex items-center gap-2">
											<div
												class="h-4 w-4 rounded-full"
												style="background-color: {nation.color}"
											></div>
											<h5 class="font-medium">{nation.name}</h5>
										</div>
										<p class="text-sm text-muted-foreground">{nation.ability}</p>
									</div>
								{/each}
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Organisation de l'équipe -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.6 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Organisation de l'équipe</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
							{#each teamRoles as role}
								<div class="rounded-lg border p-4">
									<div class="mb-3 flex items-center gap-3">
										<svelte:component this={role.icon} class="h-6 w-6 text-blue-500" />
										<h4 class="font-semibold">{role.role}</h4>
									</div>
									<p class="text-sm text-muted-foreground">{role.description}</p>
								</div>
							{/each}
						</div>
						<div
							class="mt-4 rounded-lg border border-blue-200 bg-blue-50 p-3 dark:border-blue-500/30 dark:bg-blue-500/10"
						>
							<p class="text-sm text-muted-foreground">
								<span class="font-medium">Mon rôle :</span> Développeur gameplay - J'ai contribué au
								développement des cartes, de la physique, des menus et du système de chronométrage.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Défis techniques -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.8 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Défis techniques</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
							<div class="rounded-lg border p-4">
								<h4 class="mb-2 flex items-center gap-2 font-semibold">
									<Network class="h-5 w-5 text-blue-500" />
									Synchronisation réseau
								</h4>
								<p class="text-sm text-muted-foreground">
									Mise en place de la synchronisation réseau en Pygame pour permettre le jeu
									multijoueur en temps réel.
								</p>
							</div>
							<div class="rounded-lg border p-4">
								<h4 class="mb-2 flex items-center gap-2 font-semibold">
									<Gamepad2 class="h-5 w-5 text-green-500" />
									Équilibrage des capacités
								</h4>
								<p class="text-sm text-muted-foreground">
									Équilibrage des différentes capacités des nations pour assurer une expérience de
									jeu équitable et amusante.
								</p>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Résultats -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 1.0 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Résultat final</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<p class="mb-4 leading-relaxed text-muted-foreground">
								Le jeu final permet à deux joueurs de s'affronter dans une arène. Après avoir choisi
								leur nation, l'un des joueurs commence en tant que "loup". Le but est de toucher
								l'autre joueur pour inverser les rôles.
							</p>
							<p class="leading-relaxed text-muted-foreground">
								Un chronomètre enregistre le temps passé en tant que "loup", et le joueur avec le
								temps le plus court à la fin de la partie est déclaré vainqueur. Les capacités
								spéciales de chaque nation offrent des opportunités tactiques pour attraper ou
								s'échapper.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Technologies -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 1.2 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Technologies utilisées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-2 gap-4 md:grid-cols-4">
							{#each technologies as tech}
								<a
									href={tech.url}
									target="_blank"
									class="flex items-center gap-3 rounded-lg border p-4 transition-shadow hover:shadow-md"
								>
									<div class="h-6 w-6 rounded-full" style="background-color: {tech.color}"></div>
									<span class="font-medium">{tech.name}</span>
								</a>
							{/each}
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Conclusion -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 1.4 }}
		>
			<div use:motion>
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Conclusion</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="space-y-4">
							<p class="leading-relaxed text-muted-foreground text-justify">
								Cette GameJam 2024 a été une expérience très formatrice. Elle nous a permis de
								concrétiser un projet multijoueur en Python et Pygame, en partant de zéro et en
								gérant les aspects techniques et collaboratifs en un temps record.
							</p>
							<p class="leading-relaxed text-muted-foreground text-justify">
								Le développement des mécaniques de jeu, des capacités uniques et surtout de la
								brique réseau a constitué un apprentissage significatif pour toute l'équipe. Malgré
								la pression du délai, nous sommes fiers d'avoir pu livrer un jeu fonctionnel et
								divertissant.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

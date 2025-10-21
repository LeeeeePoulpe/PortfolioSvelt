<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { ExternalLink, Calendar, Users, Gamepad2, Network, Zap } from '@lucide/svelte';

	const technologies = [
		{ name: 'Python', color: '#3776AB' },
		{ name: 'PyGame', color: '#FF6B6B' }
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
			description: 'Cartes, physique, menus, chronométrage',
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
	<meta name="description" content="Développement du jeu multijoueur Nation Chase lors de la GameJam 2024 sur le thème 'L'affrontement pacifique entre les nations'." />
</svelte:head>

<main class="min-h-screen pt-32 pb-16">
	<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8">
		<!-- Header Section -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6 }}
		>
			<div use:motion class="mb-12">
				<div class="flex flex-col lg:flex-row gap-8 items-start">
					<div class="flex-1">
						<h1 class="font-display mb-6 text-4xl font-bold text-foreground sm:text-5xl">
							GameJam 2024 - Nation Chase
						</h1>
						<p class="text-lg leading-relaxed text-muted-foreground mb-6">
							Participation à la 
							<a href="https://fr.wikipedia.org/wiki/Game_jam" target="_blank" class="text-primary hover:underline">
								GameJam
							</a> 
							2024 lors du BUT Informatique à l'IUT2 de Grenoble. Développement du jeu multijoueur 
							<a href="https://github.com/sadspear/gamejam" target="_blank" class="text-primary hover:underline">
								Nation Chase
							</a> 
							sur le thème "L'affrontement pacifique entre les nations" en équipe de 5 étudiants.
						</p>
						<div class="flex flex-wrap gap-2 mb-6">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								GameJam 2024
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Users class="h-3 w-3" />
								Équipe de 5
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Network class="h-3 w-3" />
								Multijoueur
							</Badge>
						</div>
					</div>
					<div class="flex flex-col gap-4 w-full lg:w-80">
						<a
							href="https://github.com/sadspear/gamejam"
							target="_blank"
							class="group p-4 border rounded-lg hover:shadow-lg transition-all"
						>
							<div class="flex items-center gap-3">
								<div class="w-12 h-12 bg-gradient-to-br from-red-500 to-blue-600 rounded-lg flex items-center justify-center">
									<span class="text-white font-bold text-lg">NC</span>
								</div>
								<div>
									<h3 class="font-semibold">Nation Chase</h3>
									<p class="text-sm text-muted-foreground">Repository GitHub</p>
								</div>
								<ExternalLink class="h-4 w-4 ml-auto opacity-0 group-hover:opacity-100 transition-opacity" />
							</div>
						</a>
						<div class="p-4 border rounded-lg">
							<div class="flex items-center gap-3 mb-3">
								<Zap class="h-8 w-8 text-yellow-500" />
								<div>
									<h3 class="font-semibold">GameJam 2024</h3>
									<p class="text-sm text-muted-foreground">Événement stimulant</p>
								</div>
							</div>
							<p class="text-sm text-muted-foreground">
								Conception et développement d'un jeu multijoueur en une semaine.
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
						<div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
							<div>
								<h3 class="text-xl font-semibold mb-4">La GameJam 2024</h3>
								<p class="text-muted-foreground leading-relaxed mb-4">
									Événement stimulant durant lequel des équipes d'étudiants doivent concevoir et développer un jeu vidéo 
									en respectant des contraintes de temps et de thème. Notre équipe était composée de cinq étudiants.
								</p>
								<p class="text-muted-foreground leading-relaxed">
									Le thème imposé était "L'affrontement pacifique entre les nations", avec la particularité de devoir 
									développer un jeu multijoueur en 
									<a href="https://developer.mozilla.org/fr/docs/Glossary/Python" target="_blank" class="text-primary hover:underline">
										Python
									</a> 
									et 
									<a href="https://www.pygame.org/" target="_blank" class="text-primary hover:underline">
										PyGame
									</a>.
								</p>
							</div>
							<div>
								<h3 class="text-xl font-semibold mb-4">Nation Chase</h3>
								<p class="text-muted-foreground leading-relaxed">
									Notre création baptisée "Nation Chase" est un jeu de loup touche-touche (tag) multijoueur, 
									inspiré par les 
									<a href="https://www.worldchasetag.com/" target="_blank" class="text-primary hover:underline">
										championnats du monde de Chase Tag
									</a>. 
									Chaque nation possède des capacités uniques pour dynamiser le gameplay.
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
						<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
							{#each gameMechanics as mechanic}
								<div class="p-4 border rounded-lg hover:shadow-md transition-shadow">
									<h4 class="font-semibold mb-2">{mechanic.title}</h4>
									<p class="text-sm text-muted-foreground">{mechanic.description}</p>
								</div>
							{/each}
						</div>

						<div class="mt-6 p-4 bg-gradient-to-r from-blue-50 to-purple-50 rounded-lg">
							<h4 class="font-semibold mb-3">Nations et capacités</h4>
							<div class="grid grid-cols-1 md:grid-cols-3 gap-4">
								{#each nations as nation}
									<div class="p-3 border rounded-lg">
										<div class="flex items-center gap-2 mb-2">
											<div 
												class="w-4 h-4 rounded-full" 
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
						<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
							{#each teamRoles as role}
								<div class="p-4 border rounded-lg">
									<div class="flex items-center gap-3 mb-3">
										<svelte:component this={role.icon} class="h-6 w-6 text-blue-500" />
										<h4 class="font-semibold">{role.role}</h4>
									</div>
									<p class="text-sm text-muted-foreground">{role.description}</p>
								</div>
							{/each}
						</div>
						
						<div class="mt-6 p-4 bg-gradient-to-r from-green-50 to-blue-50 rounded-lg">
							<h4 class="font-semibold mb-3">Répartition des tâches</h4>
							<div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-sm">
								<div>
									<h5 class="font-medium mb-1">Spécialiste réseau</h5>
									<p class="text-muted-foreground">Gestion complète de la communication entre joueurs</p>
								</div>
								<div>
									<h5 class="font-medium mb-1">Développeurs gameplay</h5>
									<p class="text-muted-foreground">Cartes, physique, menus, chronométrage, mécanique de changement de rôle</p>
								</div>
							</div>
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
						<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
							<div class="p-4 border rounded-lg">
								<h4 class="font-semibold mb-2 flex items-center gap-2">
									<Network class="h-5 w-5 text-blue-500" />
									Synchronisation réseau
								</h4>
								<p class="text-sm text-muted-foreground">
									Mise en place de la synchronisation réseau en Pygame pour permettre le jeu multijoueur en temps réel.
								</p>
							</div>
							<div class="p-4 border rounded-lg">
								<h4 class="font-semibold mb-2 flex items-center gap-2">
									<Gamepad2 class="h-5 w-5 text-green-500" />
									Équilibrage des capacités
								</h4>
								<p class="text-sm text-muted-foreground">
									Équilibrage des différentes capacités des nations pour assurer une expérience de jeu équitable et amusante.
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
						<CardTitle class="text-2xl">Résultats</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="text-xl font-semibold mb-4">Jeu final</h3>
							<p class="text-muted-foreground leading-relaxed mb-4">
								Le jeu final permet à deux joueurs de s'affronter dans une arène. Après avoir choisi leur nation, 
								l'un des joueurs commence en tant que "loup". Le but est de toucher l'autre joueur pour inverser les rôles.
							</p>
							<p class="text-muted-foreground leading-relaxed">
								Un chronomètre enregistre le temps passé en tant que "loup", et le joueur avec le temps le plus court 
								à la fin de la partie est déclaré vainqueur. Les capacités spéciales de chaque nation offrent des 
								opportunités tactiques pour attraper ou s'échapper.
							</p>
						</div>

						<div class="p-4 bg-gradient-to-r from-yellow-50 to-orange-50 rounded-lg">
							<h4 class="font-semibold mb-3">Défis relevés</h4>
							<div class="grid grid-cols-1 md:grid-cols-2 gap-4 text-sm">
								<div>
									<h5 class="font-medium mb-1">Développement multijoueur</h5>
									<p class="text-muted-foreground">Concrétisation d'un projet multijoueur en Python et Pygame</p>
								</div>
								<div>
									<h5 class="font-medium mb-1">Gestion du temps</h5>
									<p class="text-muted-foreground">Développement complet en un temps record</p>
								</div>
							</div>
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
						<div class="grid grid-cols-2 md:grid-cols-4 gap-4">
							{#each technologies as tech}
								<div class="flex items-center gap-3 p-4 border rounded-lg hover:shadow-md transition-shadow">
									<div 
										class="w-6 h-6 rounded-full" 
										style="background-color: {tech.color}"
									></div>
									<span class="font-medium">{tech.name}</span>
								</div>
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
							<p class="text-muted-foreground leading-relaxed">
								Cette GameJam 2024 a été une expérience très formatrice. Elle nous a permis de concrétiser un projet 
								multijoueur en Python et Pygame, en partant de zéro et en gérant les aspects techniques et collaboratifs 
								en un temps record.
							</p>
							<p class="text-muted-foreground leading-relaxed">
								Le développement des mécaniques de jeu, des capacités uniques et surtout de la brique réseau a constitué 
								un apprentissage significatif pour toute l'équipe. Malgré la pression du délai, nous sommes fiers d'avoir 
								pu livrer un jeu fonctionnel et divertissant.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

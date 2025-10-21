<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import { ExternalLink, Calendar, Users, Gamepad2, Code, Zap, ArrowLeft } from '@lucide/svelte';

	const technologies = [
		{ name: 'Python', color: '#3776AB' },
		{ name: 'PyGame', color: '#FF6B6B' }
	];

	const gameFeatures = [
		{
			title: 'Style Pokémon',
			description: 'Jeu dans le style de Pokémon se passant au premier étage de l\'IUT'
		},
		{
			title: 'Salles de boss',
			description: 'Chaque salle représente une salle de boss à affronter'
		},
		{
			title: 'Système de combat',
			description: 'Combats avec barre de rythme pour attaquer'
		},
		{
			title: 'Mécaniques de jeu',
			description: 'Soins aux toilettes, récupération des clés, boss final'
		}
	];

	const challenges = [
		'Apprendre Python en 4 jours consécutifs',
		'Développer un jeu complet en une semaine',
		'Travail en équipe sur une nouvelle technologie',
		'Respecter les contraintes de temps et de thème'
	];
</script>

<svelte:head>
	<title>GameJam 2023 - Time Striker - Hugo Föllmi</title>
	<meta name="description" content="Développement du jeu Time Striker lors de la GameJam 2023 à l'IUT2 de Grenoble sur le thème 'Le merveilleux monde de l'IUT2'." />
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
				<div class="flex flex-col lg:flex-row gap-8 items-start">
					<div class="flex-1">
						<h1 class="font-display mb-6 text-4xl font-bold text-foreground sm:text-5xl">
							GameJam 2023 - Time Striker
						</h1>
						<p class="text-lg leading-relaxed text-muted-foreground mb-6">
							Participation à la 
							<a href="https://fr.wikipedia.org/wiki/Game_jam" target="_blank" class="text-primary hover:underline">
								GameJam
							</a> 
							nationale lors du deuxième semestre du BUT Informatique à l'IUT2 de Grenoble. 
							Développement du jeu 
							<a href="https://github.com/sadspear/gamejam2023" target="_blank" class="text-primary hover:underline">
								Time Striker
							</a> 
							sur le thème "Le merveilleux monde de l'IUT2" en équipe de 4 étudiants.
						</p>
						<div class="flex flex-wrap gap-2 mb-6">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								Semestre 2 BUT
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Users class="h-3 w-3" />
								Équipe de 4
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Gamepad2 class="h-3 w-3" />
								Style Pokémon
							</Badge>
						</div>
					</div>
					<div class="flex flex-col gap-4 w-full lg:w-80">
						<a
							href="https://github.com/sadspear/gamejam2023"
							target="_blank"
							class="group p-4 border rounded-lg hover:shadow-lg transition-all"
						>
							<div class="flex items-center gap-3">
								<div class="w-12 h-12 bg-gradient-to-br from-purple-500 to-pink-600 rounded-lg flex items-center justify-center">
									<span class="text-white font-bold text-lg">TS</span>
								</div>
								<div>
									<h3 class="font-semibold">Time Striker</h3>
									<p class="text-sm text-muted-foreground">Repository GitHub</p>
								</div>
								<ExternalLink class="h-4 w-4 ml-auto opacity-0 group-hover:opacity-100 transition-opacity" />
							</div>
						</a>
						<div class="p-4 border rounded-lg">
							<div class="flex items-center gap-3 mb-3">
								<Zap class="h-8 w-8 text-yellow-500" />
								<div>
									<h3 class="font-semibold">GameJam</h3>
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
						<div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
							<div>
								<h3 class="text-xl font-semibold mb-4">La GameJam</h3>
								<p class="text-muted-foreground leading-relaxed mb-4">
									La GameJam est un événement national durant lequel les étudiants doivent réaliser un jeu vidéo 
									avec des contraintes en une semaine. Nous devions développer en 
									<a href="https://developer.mozilla.org/fr/docs/Glossary/Python" target="_blank" class="text-primary hover:underline">
										Python
									</a> 
									avec la bibliothèque 
									<a href="https://www.pygame.org/" target="_blank" class="text-primary hover:underline">
										PyGame
									</a>.
								</p>
								<p class="text-muted-foreground leading-relaxed">
									Le thème imposé était "Le merveilleux monde de l'IUT2" et nous avions le choix du style de jeu.
								</p>
							</div>
							<div>
								<h3 class="text-xl font-semibold mb-4">Time Striker</h3>
								<p class="text-muted-foreground leading-relaxed">
									Nous avons choisi de réaliser un jeu dans le style de Pokémon, se passant au premier étage de l'IUT 
									où chaque salle représente une salle de boss. Le joueur doit récupérer les clés de l'IUT et vaincre 
									le boss final : son diplôme.
								</p>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Déroulé -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.4 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Déroulé du projet</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
							<div class="p-4 border rounded-lg">
								<h3 class="text-lg font-semibold mb-3 flex items-center gap-2">
									<Code class="h-5 w-5 text-blue-500" />
									Apprentissage Python
								</h3>
								<p class="text-muted-foreground text-sm">
									Travailler quatre jours consécutifs sur une nouvelle technologie que nous ne connaissions pas était un 
									réel défi, mais aussi une expérience enrichissante.
								</p>
							</div>
							<div class="p-4 border rounded-lg">
								<h3 class="text-lg font-semibold mb-3 flex items-center gap-2">
									<Users class="h-5 w-5 text-green-500" />
									Travail d'équipe
								</h3>
								<p class="text-muted-foreground text-sm">
									L'objectif était aussi de nous faire apprendre le Python au sein de l'IUT, car c'est une matière 
									qui n'est pas enseignée dans le cursus.
								</p>
							</div>
						</div>
						
						<div>
							<h3 class="text-xl font-semibold mb-4">Mon rôle dans le projet</h3>
							<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
								<div class="p-4 border rounded-lg">
									<h4 class="font-semibold mb-2">Développement du niveau</h4>
									<p class="text-sm text-muted-foreground">
										Réalisation de l'intégralité du niveau avec l'étage de l'IUT et toutes les salles de boss.
									</p>
								</div>
								<div class="p-4 border rounded-lg">
									<h4 class="font-semibold mb-2">Système d'animation</h4>
									<p class="text-sm text-muted-foreground">
										Développement des fonctions d'animation et de déplacement du joueur.
									</p>
								</div>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Fonctionnalités du jeu -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.6 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Fonctionnalités du jeu</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
							{#each gameFeatures as feature}
								<div class="p-4 border rounded-lg hover:shadow-md transition-shadow">
									<h4 class="font-semibold mb-2">{feature.title}</h4>
									<p class="text-sm text-muted-foreground">{feature.description}</p>
								</div>
							{/each}
						</div>
						
						<div class="mt-6 p-4 bg-gradient-to-r from-purple-50 to-pink-50 rounded-lg">
							<h4 class="font-semibold mb-3">Mécaniques de gameplay</h4>
							<div class="grid grid-cols-1 md:grid-cols-3 gap-4 text-sm">
								<div>
									<h5 class="font-medium mb-1">Système de combat</h5>
									<p class="text-muted-foreground">Combats avec barre de rythme pour attaquer</p>
								</div>
								<div>
									<h5 class="font-medium mb-1">Système de soins</h5>
									<p class="text-muted-foreground">Soins en allant aux toilettes</p>
								</div>
								<div>
									<h5 class="font-medium mb-1">Objectif final</h5>
									<p class="text-muted-foreground">Récupérer les clés et vaincre le diplôme</p>
								</div>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Défis -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.8 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Défis rencontrés</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
							{#each challenges as challenge}
								<div class="flex items-start gap-3 p-4 border rounded-lg">
									<div class="w-2 h-2 bg-orange-500 rounded-full mt-2 flex-shrink-0"></div>
									<p class="text-muted-foreground">{challenge}</p>
								</div>
							{/each}
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
			transition={{ duration: 0.6, delay: 1.0 }}
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

		<!-- Résultats -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 1.2 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Résultats</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="space-y-4">
							<p class="text-muted-foreground leading-relaxed">
								Notre jeu reprend le principe de Pokémon, où le joueur doit affronter des ennemis dans des combats à l'aide 
								d'une barre de rythme pour attaquer. Le joueur peut également se soigner en allant aux toilettes.
							</p>
							<p class="text-muted-foreground leading-relaxed">
								Pour sortir de l'IUT, le joueur doit récupérer les clés de l'IUT et vaincre le boss final : son diplôme. 
								Les clés sont cachées dans les salles de cours qui chacune représente un partiel.
							</p>
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
								Cette GameJam a été une expérience enrichissante qui nous a permis d'apprendre une nouvelle technologie, 
								le Python, et de travailler en équipe. Malgré les difficultés de délais rencontrées, nous avons réussi 
								à réaliser un jeu vidéo en une semaine.
							</p>
							<p class="text-muted-foreground leading-relaxed">
								Ce projet nous a permis d'acquérir de nouvelles compétences et de renforcer notre cohésion en tant qu'équipe. 
								L'apprentissage accéléré d'une nouvelle technologie dans un contexte de pression temporelle a été particulièrement 
								formateur pour notre développement professionnel.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

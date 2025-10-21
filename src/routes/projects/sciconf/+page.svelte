<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Calendar, Users, Database, Code, CheckCircle, Lightbulb } from '@lucide/svelte';

	const technologies = [
		{ name: 'Java', color: '#007396' },
		{ name: 'JavaFX', color: '#FF6B6B' },
		{ name: 'MySQL', color: '#4479A1' }
	];

	const projectSteps = [
		{
			step: '1',
			title: 'Réflexion',
			description: 'Définition de l\'application de gestion d\'événements',
			icon: Lightbulb
		},
		{
			step: '2',
			title: 'Conception',
			description: 'Réalisation de maquettes pour visualiser l\'interface',
			icon: CheckCircle
		},
		{
			step: '3',
			title: 'Développement',
			description: 'Implémentation en Java avec JavaFX et MySQL',
			icon: Code
		},
		{
			step: '4',
			title: 'Tests',
			description: 'Vérification du bon fonctionnement de l\'application',
			icon: CheckCircle
		}
	];

	const features = [
		{
			title: 'Gestion des conférences',
			description: 'Création, modification et suppression des conférences scientifiques'
		},
		{
			title: 'Gestion des intervenants',
			description: 'Inscription et suivi des intervenants pour chaque conférence'
		},
		{
			title: 'Gestion des participants',
			description: 'Inscription et suivi des participants aux conférences'
		},
		{
			title: 'Gestion des salles',
			description: 'Attribution et gestion des salles pour les événements'
		}
	];

	const achievements = [
		'Application conforme aux maquettes et contraintes',
		'Gestion complète des conférences, intervenants, participants et salles',
		'Respect des délais imposés par l\'IUT',
		'Travail d\'équipe efficace avec répartition équitable des tâches'
	];
</script>

<svelte:head>
	<title>Sciconf - Hugo Föllmi</title>
	<meta name="description" content="Développement d'une application de gestion d'événements scientifiques avec Java, JavaFX et MySQL lors du second semestre du BUT Informatique." />
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
							Sciconf
						</h1>
						<p class="text-lg leading-relaxed text-muted-foreground mb-6">
							Application de gestion d'événements scientifiques développée lors du second semestre du BUT Informatique 
							à l'IUT2 de Grenoble. Projet réalisé en équipe de 5 étudiants pour gérer les conférences, intervenants, 
							participants et salles.
						</p>
						<div class="flex flex-wrap gap-2 mb-6">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								Semestre 2 BUT
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Users class="h-3 w-3" />
								Équipe de 5
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Database class="h-3 w-3" />
								Java & MySQL
							</Badge>
						</div>
					</div>
					<div class="flex flex-col gap-4 w-full lg:w-80">
						<div class="p-4 border rounded-lg">
							<div class="flex items-center gap-3 mb-3">
								<Database class="h-8 w-8 text-blue-500" />
								<div>
									<h3 class="font-semibold">Sciconf</h3>
									<p class="text-sm text-muted-foreground">Gestion d'événements</p>
								</div>
							</div>
							<p class="text-sm text-muted-foreground">
								Application de gestion des conférences scientifiques avec interface JavaFX.
							</p>
						</div>
						<div class="p-4 border rounded-lg">
							<div class="flex items-center gap-3 mb-3">
								<Code class="h-8 w-8 text-green-500" />
								<div>
									<h3 class="font-semibold">Technologies</h3>
									<p class="text-sm text-muted-foreground">Java, JavaFX, MySQL</p>
								</div>
							</div>
							<p class="text-sm text-muted-foreground">
								Back-end en Java, front-end en JavaFX, base de données MySQL.
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
								<h3 class="text-xl font-semibold mb-4">Objectif pédagogique</h3>
								<p class="text-muted-foreground leading-relaxed mb-4">
									L'objectif du projet était de nous faire comprendre toutes les étapes du déroulé d'un projet : 
									de la réflexion à la réalisation en passant par la conception. Nous avions le choix sur le type 
									d'événement et avons choisi les conférences scientifiques.
								</p>
								<p class="text-muted-foreground leading-relaxed">
									L'application devait permettre de gérer les conférences, les intervenants, les participants et les salles.
								</p>
							</div>
							<div>
								<h3 class="text-xl font-semibold mb-4">Contraintes techniques</h3>
								<div class="space-y-3">
									<div class="p-3 border rounded-lg">
										<h4 class="font-semibold mb-1 flex items-center gap-2">
											<Code class="h-4 w-4 text-blue-500" />
											Back-end
										</h4>
										<p class="text-sm text-muted-foreground">
											<a href="https://developer.mozilla.org/fr/docs/Glossary/Java" target="_blank" class="text-primary hover:underline">
												Java
											</a> 
											obligatoire pour le développement
										</p>
									</div>
									<div class="p-3 border rounded-lg">
										<h4 class="font-semibold mb-1 flex items-center gap-2">
											<Database class="h-4 w-4 text-green-500" />
											Front-end
										</h4>
										<p class="text-sm text-muted-foreground">
											<a href="https://openjfx.io/" target="_blank" class="text-primary hover:underline">
												JavaFX
											</a> 
											pour l'interface utilisateur
										</p>
									</div>
									<div class="p-3 border rounded-lg">
										<h4 class="font-semibold mb-1 flex items-center gap-2">
											<Database class="h-4 w-4 text-purple-500" />
											Base de données
										</h4>
										<p class="text-sm text-muted-foreground">MySQL pour le stockage des données</p>
									</div>
								</div>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Étapes du projet -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.4 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Étapes du développement</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
							{#each projectSteps as step}
								<div class="text-center p-4 border rounded-lg hover:shadow-md transition-shadow">
									<div class="w-12 h-12 bg-gradient-to-br from-blue-500 to-purple-600 rounded-full flex items-center justify-center mx-auto mb-3">
										<svelte:component this={step.icon} class="h-6 w-6 text-white" />
									</div>
									<div class="w-8 h-8 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-3">
										<span class="text-blue-600 font-semibold text-sm">{step.step}</span>
									</div>
									<h3 class="font-semibold mb-2">{step.title}</h3>
									<p class="text-sm text-muted-foreground">{step.description}</p>
								</div>
							{/each}
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Fonctionnalités -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.6 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Fonctionnalités développées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
							{#each features as feature}
								<div class="p-4 border rounded-lg hover:shadow-md transition-shadow">
									<h4 class="font-semibold mb-2">{feature.title}</h4>
									<p class="text-sm text-muted-foreground">{feature.description}</p>
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
			transition={{ duration: 0.6, delay: 0.8 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Résultats obtenus</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
							{#each achievements as achievement}
								<div class="flex items-start gap-3 p-4 border rounded-lg">
									<CheckCircle class="h-5 w-5 text-green-500 mt-0.5 flex-shrink-0" />
									<p class="text-muted-foreground">{achievement}</p>
								</div>
							{/each}
						</div>

						<div class="p-4 bg-gradient-to-r from-green-50 to-blue-50 rounded-lg">
							<h4 class="font-semibold mb-3">Succès du projet</h4>
							<p class="text-muted-foreground text-sm">
								Nous avons réussi à développer cette application grâce à notre travail d'équipe et à notre 
								répartition équitable des tâches en fonction des compétences de chacun. Le respect des délais 
								imposés par l'IUT et la conformité aux contraintes techniques ont été des éléments clés du succès.
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
			transition={{ duration: 0.6, delay: 1.0 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Technologies utilisées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-2 md:grid-cols-3 gap-4">
							{#each technologies as tech}
								<div class="flex items-center gap-3 p-3 border rounded-lg hover:shadow-md transition-shadow">
									<div 
										class="w-4 h-4 rounded-full" 
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
			transition={{ duration: 0.6, delay: 1.2 }}
		>
			<div use:motion>
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Conclusion</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="space-y-4">
							<p class="text-muted-foreground leading-relaxed">
								Ce projet nous a permis de comprendre toutes les étapes d'un projet, de la réflexion à la réalisation. 
								Nous avons également appris à travailler en équipe pour réaliser un projet complet.
							</p>
							<p class="text-muted-foreground leading-relaxed">
								Ce projet nous a permis de mettre en pratique les connaissances acquises lors de notre formation, 
								notamment en 
								<a href="https://developer.mozilla.org/fr/docs/Glossary/Java" target="_blank" class="text-primary hover:underline">
									Java
								</a> 
								et 
								<a href="https://openjfx.io/" target="_blank" class="text-primary hover:underline">
									JavaFX
								</a>, 
								ainsi que la gestion de base de données avec MySQL.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

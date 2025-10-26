<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import {
		Calendar,
		Users,
		Database,
		Code,
		CheckCircle,
		Lightbulb,
		ArrowLeft
	} from '@lucide/svelte';

	const technologies = [
		{ name: 'Java', color: '#007396', url: 'https://www.java.com/' },
		{ name: 'JavaFX', color: '#FF6B6B', url: 'https://openjfx.io/' },
		{ name: 'MySQL', color: '#4479A1', url: 'https://www.mysql.com/' }
	];

	const projectSteps = [
		{
			step: '1',
			title: 'Réflexion',
			description: "Définition de l'application de gestion d'événements",
			icon: Lightbulb
		},
		{
			step: '2',
			title: 'Conception',
			description: "Réalisation de maquettes pour visualiser l'interface",
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
			description: "Vérification du bon fonctionnement de l'application",
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
		"Respect des délais imposés par l'IUT",
		"Travail d'équipe efficace avec répartition équitable des tâches"
	];
</script>

<svelte:head>
	<title>Sciconf - Hugo Föllmi</title>
	<meta
		name="description"
		content="Développement d'une application de gestion d'événements scientifiques avec Java, JavaFX et MySQL lors du second semestre du BUT Informatique."
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
							Sciconf
						</h1>
						<p class="mb-6 text-lg leading-relaxed text-muted-foreground">
							Application de gestion d'événements scientifiques développée lors du second semestre
							du BUT Informatique à l'IUT2 de Grenoble. Projet réalisé en équipe de 5 étudiants pour
							gérer les conférences, intervenants, participants et salles.
						</p>
						<div class="mb-6 flex flex-wrap gap-2">
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
					<div class="flex w-full flex-col gap-4 lg:w-80">
						<div class="rounded-lg border p-4">
							<div class="mb-3 flex items-center gap-3">
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
						<div class="rounded-lg border p-4">
							<div class="mb-3 flex items-center gap-3">
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
						<div class="grid grid-cols-1 gap-8 lg:grid-cols-2">
							<div>
								<h3 class="mb-4 text-xl font-semibold">Objectif pédagogique</h3>
								<p class="mb-4 leading-relaxed text-muted-foreground">
									L'objectif du projet était de nous faire comprendre toutes les étapes du déroulé
									d'un projet : de la réflexion à la réalisation en passant par la conception. Nous
									avions le choix sur le type d'événement et avons choisi les conférences
									scientifiques.
								</p>
								<p class="leading-relaxed text-muted-foreground">
									L'application devait permettre de gérer les conférences, les intervenants, les
									participants et les salles.
								</p>
							</div>
							<div>
								<h3 class="mb-4 text-xl font-semibold">Contraintes techniques</h3>
								<div class="space-y-3">
									<div class="rounded-lg border p-3">
										<h4 class="mb-1 flex items-center gap-2 font-semibold">
											<Code class="h-4 w-4 text-blue-500" />
											Back-end
										</h4>
										<p class="text-sm text-muted-foreground">
											<a
												href="https://developer.mozilla.org/fr/docs/Glossary/Java"
												target="_blank"
												class="text-primary hover:underline"
											>
												Java
											</a>
											obligatoire pour le développement
										</p>
									</div>
									<div class="rounded-lg border p-3">
										<h4 class="mb-1 flex items-center gap-2 font-semibold">
											<Database class="h-4 w-4 text-green-500" />
											Front-end
										</h4>
										<p class="text-sm text-muted-foreground">
											<a
												href="https://openjfx.io/"
												target="_blank"
												class="text-primary hover:underline"
											>
												JavaFX
											</a>
											pour l'interface utilisateur
										</p>
									</div>
									<div class="rounded-lg border p-3">
										<h4 class="mb-1 flex items-center gap-2 font-semibold">
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
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-4">
							{#each projectSteps as step}
								<div class="rounded-lg border p-4 text-center transition-shadow hover:shadow-md">
									<div
										class="mx-auto mb-3 flex h-12 w-12 items-center justify-center rounded-full bg-gradient-to-br from-blue-500 to-purple-600"
									>
										<svelte:component this={step.icon} class="h-6 w-6 text-white" />
									</div>
									<div
										class="mx-auto mb-3 flex h-8 w-8 items-center justify-center rounded-full bg-blue-100"
									>
										<span class="text-sm font-semibold text-blue-600">{step.step}</span>
									</div>
									<h3 class="mb-2 font-semibold">{step.title}</h3>
									<p class="text-sm text-muted-foreground">{step.description}</p>
								</div>
							{/each}
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
			transition={{ duration: 0.6, delay: 0.5 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Organisation de l'équipe</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="rounded-lg border border-blue-200 bg-blue-50 p-4">
							<p class="text-sm text-muted-foreground">
								<span class="font-medium">Équipe :</span> Projet réalisé en équipe de 5 étudiants avec
								une répartition équitable des tâches en fonction des compétences de chacun. Le travail
								d'équipe et la communication ont été des éléments clés pour le respect des délais
								imposés par l'IUT et la conformité aux contraintes techniques.
							</p>
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
			transition={{ duration: 0.6, delay: 0.7 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Fonctionnalités développées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
							{#each features as feature}
								<div class="rounded-lg border p-4 transition-shadow hover:shadow-md">
									<h4 class="mb-2 font-semibold">{feature.title}</h4>
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
			transition={{ duration: 0.6, delay: 0.9 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Résultats obtenus</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
							{#each achievements as achievement}
								<div class="flex items-start gap-3 rounded-lg border p-4">
									<CheckCircle class="mt-0.5 h-5 w-5 flex-shrink-0 text-green-500" />
									<p class="text-muted-foreground">{achievement}</p>
								</div>
							{/each}
						</div>

						<div class="rounded-lg bg-gradient-to-r from-green-50 to-blue-50 p-4">
							<h4 class="mb-3 font-semibold">Succès du projet</h4>
							<p class="text-sm text-muted-foreground">
								Nous avons réussi à développer cette application grâce à notre travail d'équipe et à
								notre répartition équitable des tâches en fonction des compétences de chacun. Le
								respect des délais imposés par l'IUT et la conformité aux contraintes techniques ont
								été des éléments clés du succès.
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
			transition={{ duration: 0.6, delay: 1.1 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Technologies utilisées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-2 gap-4 md:grid-cols-3">
							{#each technologies as tech}
								<a
									href={tech.url}
									target="_blank"
									class="flex items-center gap-3 rounded-lg border p-3 transition-shadow hover:shadow-md"
								>
									<div class="h-4 w-4 rounded-full" style="background-color: {tech.color}"></div>
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
			transition={{ duration: 0.6, delay: 1.3 }}
		>
			<div use:motion>
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Conclusion</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="space-y-4">
							<p class="leading-relaxed text-muted-foreground">
								Ce projet nous a permis de comprendre toutes les étapes d'un projet, de la réflexion
								à la réalisation. Nous avons également appris à travailler en équipe pour réaliser
								un projet complet.
							</p>
							<p class="leading-relaxed text-muted-foreground">
								Ce projet nous a permis de mettre en pratique les connaissances acquises lors de
								notre formation, notamment en
								<a
									href="https://developer.mozilla.org/fr/docs/Glossary/Java"
									target="_blank"
									class="text-primary hover:underline"
								>
									Java
								</a>
								et
								<a href="https://openjfx.io/" target="_blank" class="text-primary hover:underline">
									JavaFX
								</a>, ainsi que la gestion de base de données avec MySQL.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

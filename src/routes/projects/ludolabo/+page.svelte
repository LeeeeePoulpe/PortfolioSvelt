<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import {
		ExternalLink,
		Calendar,
		Users,
		GraduationCap,
		Gamepad2,
		ArrowLeft
	} from '@lucide/svelte';

	const technologies = [
		{ name: 'Vue.js', color: '#4FC08D', url: 'https://vuejs.org/' },
		{ name: 'Tailwind CSS', color: '#06B6D4', url: 'https://tailwindcss.com/' },
		{ name: 'PrelineUI', color: '#8B5CF6', url: 'https://preline.co/' },
		{ name: 'Unity', color: '#000000', url: 'https://unity.com/' }
	];

	const worlds = [
		{
			name: 'Les lacs chimiques',
			description: 'Questions sur les réactions chimiques et les molécules',
			color: '#3B82F6'
		},
		{
			name: 'Les terres cinétiques',
			description: 'Questions sur les forces et les mouvements',
			color: '#10B981'
		},
		{
			name: 'Autres mondes',
			description: 'Chapitres supplémentaires de physique-chimie',
			color: '#8B5CF6'
		}
	];

	const features = [
		{
			title: 'Système de classes',
			description: 'Les professeurs créent des classes que les élèves rejoignent avec un code'
		},
		{
			title: 'Jeux de révision',
			description: 'Questions de physique-chimie avec système de points et classement'
		},
		{
			title: 'Suivi des progrès',
			description: 'Tableaux de bord pour professeurs avec diagrammes de progression'
		},
		{
			title: 'Gestion des chapitres',
			description: 'Organisation des mondes par chapitre de physique-chimie'
		}
	];

	const challenges = [
		'Développement en 3 semaines consécutives',
		'Équipe de 8 personnes à coordonner',
		'Passage de Faser.js à Unity pour les performances',
		'Respect du cahier des charges en temps limité'
	];
</script>

<svelte:head>
	<title>LudoLabo - Hugo Föllmi</title>
	<meta
		name="description"
		content="Développement de LudoLabo, une application ludique pour aider les élèves de terminale à réviser la physique-chimie."
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
							LudoLabo
						</h1>
						<p class="mb-6 text-lg leading-relaxed text-muted-foreground">
							Interface et jeu ludiques pour aider les élèves de terminale à réviser leur
							enseignement de spécialité en physique-chimie et permettre aux professeurs de suivre
							les progrès. Projet réalisé dans le cadre du BUT Informatique à l'IUT2 de Grenoble
							lors du troisième semestre, en équipe de 8 personnes.
						</p>
						<div class="mb-6 flex flex-wrap gap-2">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								2e année de BUT
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Users class="h-3 w-3" />
								Équipe de 8 personnes
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<GraduationCap class="h-3 w-3" />
								Éducation
							</Badge>
						</div>
					</div>
					<div class="flex w-full flex-col gap-4 lg:w-80">
						<a
							href="https://github.com/LudoLaboApp"
							target="_blank"
							class="group rounded-lg border p-4 transition-all hover:shadow-lg"
						>
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 items-center justify-center rounded-lg bg-gradient-to-br from-green-500 to-blue-600"
								>
									<span class="text-lg font-bold text-white">LL</span>
								</div>
								<div>
									<h3 class="font-semibold">LudoLabo</h3>
									<p class="text-sm text-muted-foreground">Repository GitHub</p>
								</div>
								<ExternalLink
									class="ml-auto h-4 w-4 opacity-0 transition-opacity group-hover:opacity-100"
								/>
							</div>
						</a>
						<div class="rounded-lg border p-4">
							<div class="mb-3 flex items-center gap-3">
								<Gamepad2 class="h-8 w-8 text-purple-500" />
								<div>
									<h3 class="font-semibold">Jeu éducatif</h3>
									<p class="text-sm text-muted-foreground">Physique-chimie ludique</p>
								</div>
							</div>
							<p class="text-sm text-muted-foreground">
								Application web + jeu Unity pour réviser la physique-chimie.
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
								<h3 class="mb-4 text-xl font-semibold">Objectif éducatif</h3>
								<p class="mb-4 leading-relaxed text-muted-foreground">
									Le jeu devait être basé sur des questions et des énigmes des différents chapitres
									de physique-chimie vus en terminale. Chaque bonne réponse permettait aux élèves de
									gagner des points et de réaliser un classement entre les élèves d'une même classe.
								</p>
								<p class="leading-relaxed text-muted-foreground">
									L'objectif était de rendre le processus de révision ludique et de le relier à des
									situations de la vie quotidienne pour rendre l'apprentissage plus attrayant.
								</p>
							</div>
							<div>
								<h3 class="mb-4 text-xl font-semibold">Public cible</h3>
								<div class="space-y-3">
									<div class="rounded-lg border p-3">
										<h4 class="mb-1 flex items-center gap-2 font-semibold">
											<GraduationCap class="h-4 w-4 text-blue-500" />
											Élèves de terminale
										</h4>
										<p class="text-sm text-muted-foreground">
											Révision de l'enseignement de spécialité en physique-chimie
										</p>
									</div>
									<div class="rounded-lg border p-3">
										<h4 class="mb-1 flex items-center gap-2 font-semibold">
											<Users class="h-4 w-4 text-green-500" />
											Professeurs
										</h4>
										<p class="text-sm text-muted-foreground">
											Suivi des progrès et identification des lacunes
										</p>
									</div>
								</div>
							</div>
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
			transition={{ duration: 0.6, delay: 0.4 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Fonctionnalités développées</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
							{#each features as feature}
								<div class="rounded-lg border p-4 transition-shadow hover:shadow-md">
									<h4 class="mb-2 font-semibold">{feature.title}</h4>
									<p class="text-sm text-muted-foreground">{feature.description}</p>
								</div>
							{/each}
						</div>

						<div class="mt-6 rounded-lg bg-gradient-to-r from-blue-50 to-purple-50 p-4">
							<h4 class="mb-3 font-semibold">Mondes de révision</h4>
							<div class="grid grid-cols-1 gap-4 md:grid-cols-3">
								{#each worlds as world}
									<div class="rounded-lg border p-3">
										<div class="mb-2 flex items-center gap-2">
											<div
												class="h-4 w-4 rounded-full"
												style="background-color: {world.color}"
											></div>
											<h5 class="font-medium">{world.name}</h5>
										</div>
										<p class="text-sm text-muted-foreground">{world.description}</p>
									</div>
								{/each}
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
			transition={{ duration: 0.6, delay: 0.6 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Résultats obtenus</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div class="grid grid-cols-1 gap-8 lg:grid-cols-2">
							<div>
								<h3 class="mb-4 text-xl font-semibold">Plateforme web</h3>
								<p class="mb-4 leading-relaxed text-muted-foreground">
									<a
										href="https://github.com/LudoLaboApp/ludolabo-client"
										target="_blank"
										class="text-primary hover:underline"
									>
										Plateforme web
									</a>
									permettant aux professeurs de suivre les progrès de leurs élèves avec un système de
									classe. Les élèves peuvent rejoindre une classe et participer à des jeux de révision.
								</p>
								<ul class="space-y-1 text-sm text-muted-foreground">
									<li>• Système de codes de classe</li>
									<li>• Gestion des élèves et des classes</li>
									<li>• Diagrammes de progression</li>
									<li>• Suivi des réponses des élèves</li>
								</ul>
							</div>
							<div>
								<h3 class="mb-4 text-xl font-semibold">Jeu Unity</h3>
								<p class="mb-4 leading-relaxed text-muted-foreground">
									<a
										href="https://github.com/LudoLaboApp/ludolabo-game"
										target="_blank"
										class="text-primary hover:underline"
									>
										Jeu développé en Unity
									</a>
									avec des mondes représentant différents chapitres de physique-chimie. Chaque monde
									contient des questions sur un thème particulier.
								</p>
								<ul class="space-y-1 text-sm text-muted-foreground">
									<li>• Mondes thématiques (lacs chimiques, terres cinétiques)</li>
									<li>• Système de points et classement</li>
									<li>• Questions adaptées au niveau terminale</li>
									<li>• Interface intuitive et engageante</li>
								</ul>
							</div>
						</div>

						<div class="rounded-lg bg-gradient-to-r from-green-50 to-blue-50 p-4">
							<h4 class="mb-3 font-semibold">Fonctionnalités avancées</h4>
							<div class="grid grid-cols-1 gap-4 text-sm md:grid-cols-2">
								<div>
									<h5 class="mb-1 font-medium">Gestion des classes</h5>
									<p class="text-muted-foreground">
										Ajout d'élèves, changement de l'ordre des chapitres
									</p>
								</div>
								<div>
									<h5 class="mb-1 font-medium">Analytics détaillés</h5>
									<p class="text-muted-foreground">Points forts et faibles de chaque élève</p>
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
						<div class="grid grid-cols-1 gap-4 md:grid-cols-2">
							{#each challenges as challenge}
								<div class="flex items-start gap-3 rounded-lg border p-4">
									<div class="mt-2 h-2 w-2 flex-shrink-0 rounded-full bg-orange-500"></div>
									<p class="text-muted-foreground">{challenge}</p>
								</div>
							{/each}
						</div>

						<div class="mt-6 rounded-lg bg-gradient-to-r from-yellow-50 to-orange-50 p-4">
							<h4 class="mb-3 font-semibold">Décision technique importante</h4>
							<p class="text-sm text-muted-foreground">
								Initialement prévu avec Faser.js, nous avons finalement décidé de réaliser le jeu en
								Unity pour des raisons de performance et de facilité de développement, malgré le
								changement de technologie en cours de projet.
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
						<div class="grid grid-cols-2 gap-4 md:grid-cols-3 lg:grid-cols-5">
							{#each technologies as tech}
								<a
									href={tech.url}
									target="_blank"
									class="flex items-center gap-3 rounded-lg border p-3 transition-shadow hover:shadow-md"
								>
									<div class="h-4 w-4 rounded-full" style="background-color: {tech.color}"></div>
									<span class="text-sm font-medium">{tech.name}</span>
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
			transition={{ duration: 0.6, delay: 1.2 }}
		>
			<div use:motion>
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Conclusion</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="space-y-4">
							<p class="leading-relaxed text-muted-foreground">
								Ce projet a été une expérience très enrichissante car j'ai eu l'occasion de
								m'intégrer dans une équipe plus conséquente par rapport aux projets précédents. J'ai
								participé à la réalisation de l'interface web en utilisant Vue.js, une technologie
								déjà utilisée, complétée avec Tailwind CSS et PrelineUI.
							</p>
							<p class="leading-relaxed text-muted-foreground">
								Ce projet a aussi été un énorme défi car nous avons réalisé l'application et le jeu
								en respectant les critères du cahier des charges en seulement trois semaines.
								L'adaptation au changement de technologie (Faser.js vers Unity) en cours de projet a
								été particulièrement formatrice.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

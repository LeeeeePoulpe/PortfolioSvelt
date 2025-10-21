<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { ExternalLink, Calendar, Users, Gamepad2, Lightbulb, Target } from '@lucide/svelte';

	const technologies = [
		{ name: 'Vue.js 3', color: '#4FC08D' },
		{ name: 'JavaScript', color: '#F7DF1E' },
		{ name: 'Vuetify', color: '#1867C0' },
		{ name: 'GitLab', color: '#FCA326' },
		{ name: 'Figma', color: '#F24E1E' },
		{ name: 'IntelliJ IDEA', color: '#000000' }
	];

	const deliverables = [
		{
			title: 'Jeu interactif "Au pas de course !"',
			description: 'Illustration du principe de groupement/proximité à travers un jeu de course dans des rayons de supermarché',
			type: 'professionnel'
		},
		{
			title: 'Page explicative du principe',
			description: 'Documentation détaillée du concept de groupement/proximité avec exemples concrets',
			type: 'professionnel'
		},
		{
			title: 'Documentation technique',
			description: 'Journal de bord hebdomadaire et documentation technique complète',
			type: 'personnel'
		}
	];

	const team = [
		{
			name: 'Benoît Dumas',
			role: 'Maître de stage',
			description: 'Encadrement et directives',
			linkedin: 'https://www.linkedin.com/in/benoit-dumas/'
		},
		{
			name: 'Margaux Perrin',
			role: 'Product Owner',
			description: 'Validation des réalisations et ajustement des tâches',
			linkedin: 'https://www.linkedin.com/in/margaux-lergo/'
		},
		{
			name: 'Antoine Dubois',
			role: 'Développeur',
			description: 'Aide sur des aspects techniques spécifiques',
			linkedin: 'https://www.linkedin.com/in/antoine-du-bois-60b429196/'
		},
		{
			name: 'Benjamin Biguet',
			role: 'Designer',
			description: 'Création des maquettes et scénarios',
			linkedin: 'https://www.linkedin.com/in/benjaminbiguet/'
		}
	];
</script>

<svelte:head>
	<title>ErgoGames - Hugo Föllmi</title>
	<meta name="description" content="Développement du sixième jeu des ErgoGames 'Au pas de course !' chez Sogilis pour enseigner le principe ergonomique du groupement/proximité." />
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
							ErgoGames - Au pas de course !
						</h1>
						<p class="text-lg leading-relaxed text-muted-foreground mb-6">
							Développement du sixième jeu des 
							<a href="https://www.ergogames.fr/" target="_blank" class="text-primary hover:underline">
								ErgoGames
							</a> 
							chez 
							<a href="https://sogilis.com/" target="_blank" class="text-primary hover:underline">
								Sogilis
							</a>. 
							Ce jeu a pour objectif de présenter le principe ergonomique du groupement/proximité de manière 
							simple et ludique, avec une représentation visuelle interactive.
						</p>
						<div class="flex flex-wrap gap-2 mb-6">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								Stage Sogilis
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Gamepad2 class="h-3 w-3" />
								Jeu interactif
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Lightbulb class="h-3 w-3" />
								Principe ergonomique
							</Badge>
						</div>
					</div>
					<div class="flex flex-col gap-4 w-full lg:w-80">
						<a
							href="https://www.ergogames.fr/"
							target="_blank"
							class="group p-4 border rounded-lg hover:shadow-lg transition-all"
						>
							<div class="flex items-center gap-3">
								<div class="w-12 h-12 bg-gradient-to-br from-yellow-500 to-orange-600 rounded-lg flex items-center justify-center">
									<span class="text-white font-bold text-lg">EG</span>
								</div>
								<div>
									<h3 class="font-semibold">ErgoGames</h3>
									<p class="text-sm text-muted-foreground">Site des ErgoGames</p>
								</div>
								<ExternalLink class="h-4 w-4 ml-auto opacity-0 group-hover:opacity-100 transition-opacity" />
							</div>
						</a>
						<a
							href="https://sogilis.com/"
							target="_blank"
							class="group p-4 border rounded-lg hover:shadow-lg transition-all"
						>
							<div class="flex items-center gap-3">
								<div class="w-12 h-12 bg-gradient-to-br from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
									<span class="text-white font-bold text-lg">S</span>
								</div>
								<div>
									<h3 class="font-semibold">Sogilis</h3>
									<p class="text-sm text-muted-foreground">Entreprise de génie logiciel</p>
								</div>
								<ExternalLink class="h-4 w-4 ml-auto opacity-0 group-hover:opacity-100 transition-opacity" />
							</div>
						</a>
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
								<h3 class="text-xl font-semibold mb-4">Les ErgoGames</h3>
								<p class="text-muted-foreground leading-relaxed mb-4">
									Le site des ErgoGames est conçu pour présenter de manière ludique les principes ergonomiques du numérique, 
									tels que les actions minimales ou la gestion des erreurs. Il propose des jeux et un quiz pour faciliter 
									l'apprentissage de ces principes.
								</p>
								<p class="text-muted-foreground leading-relaxed">
									Mon sujet de stage portait sur le développement du sixième jeu "Au pas de course !" qui illustre le 
									principe ergonomique du groupement/proximité.
								</p>
							</div>
							<div>
								<h3 class="text-xl font-semibold mb-4">Sogilis</h3>
								<p class="text-muted-foreground leading-relaxed">
									Entreprise de génie logiciel basée à Grenoble, spécialisée dans la création de solutions sur mesure 
									de haute qualité pour divers secteurs industriels. Elle se distingue par ses valeurs fortes et son 
									engagement envers la qualité, l'innovation et l'expérience utilisateur.
								</p>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Objectifs -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.4 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Objectifs du projet</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
							<div class="text-center p-4 border rounded-lg">
								<div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-3">
									<Target class="h-6 w-6 text-blue-600" />
								</div>
								<h3 class="font-semibold mb-2">Enseigner le principe</h3>
								<p class="text-sm text-muted-foreground">
									Développer un jeu interactif pour enseigner le principe ergonomique du groupement/proximité.
								</p>
							</div>
							<div class="text-center p-4 border rounded-lg">
								<div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-3">
									<Gamepad2 class="h-6 w-6 text-green-600" />
								</div>
								<h3 class="font-semibold mb-2">Interface intuitive</h3>
								<p class="text-sm text-muted-foreground">
									Créer une interface utilisateur intuitive et accessible pour tous les niveaux de joueurs.
								</p>
							</div>
							<div class="text-center p-4 border rounded-lg">
								<div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mx-auto mb-3">
									<Lightbulb class="h-6 w-6 text-purple-600" />
								</div>
								<h3 class="font-semibold mb-2">Page explicative</h3>
								<p class="text-sm text-muted-foreground">
									Développer une page dédiée à l'explication détaillée du principe ergonomique.
								</p>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Réalisations -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.6 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Réalisations</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="text-xl font-semibold mb-4">Le jeu "Au pas de course !"</h3>
							<p class="text-muted-foreground leading-relaxed mb-6">
								Le jeu consiste à réaliser des courses dans des rayons de supermarchés, divisé en deux parties :
							</p>
							<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
								<div class="p-4 border rounded-lg">
									<h4 class="font-semibold mb-2 text-blue-600">Première partie</h4>
									<p class="text-sm text-muted-foreground">Affichage aléatoire des produits dans les rayons</p>
								</div>
								<div class="p-4 border rounded-lg">
									<h4 class="font-semibold mb-2 text-green-600">Deuxième partie</h4>
									<p class="text-sm text-muted-foreground">Affichage organisé selon le principe de groupement</p>
								</div>
							</div>
						</div>

						<div>
							<h3 class="text-xl font-semibold mb-4">Livrables</h3>
							<div class="space-y-4">
								{#each deliverables as deliverable}
									<div class="p-4 border rounded-lg">
										<div class="flex items-start gap-3">
											<div class="w-8 h-8 rounded-full flex items-center justify-center flex-shrink-0 {deliverable.type === 'professionnel' ? 'bg-blue-100' : 'bg-green-100'}">
												<span class="text-xs font-semibold {deliverable.type === 'professionnel' ? 'text-blue-600' : 'text-green-600'}">
													{deliverable.type === 'professionnel' ? 'P' : 'L'}
												</span>
											</div>
											<div>
												<h4 class="font-semibold">{deliverable.title}</h4>
												<p class="text-sm text-muted-foreground">{deliverable.description}</p>
											</div>
										</div>
									</div>
								{/each}
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
			transition={{ duration: 0.6, delay: 0.8 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Technologies utilisées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
							{#each technologies as tech}
								<div class="flex items-center gap-3 p-3 border rounded-lg hover:shadow-md transition-shadow">
									<div 
										class="w-4 h-4 rounded-full" 
										style="background-color: {tech.color}"
									></div>
									<span class="font-medium text-sm">{tech.name}</span>
								</div>
							{/each}
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Équipe -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 1.0 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Méthodologie et équipe</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="text-xl font-semibold mb-4">Méthode SCRUM</h3>
							<p class="text-muted-foreground leading-relaxed mb-4">
								Le projet a été organisé en utilisant la méthode SCRUM, fonctionnant par cycles de deux semaines (sprints). 
								Chaque sprint comprenait une réunion quotidienne (Daily) pour le suivi des tâches, ainsi qu'une réunion de fin 
								de sprint combinant Sprint Review, Sprint Retrospective et Sprint Planning.
							</p>
						</div>

						<div>
							<h3 class="text-xl font-semibold mb-4">Équipe de développement</h3>
							<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
								{#each team as member}
									<div class="p-4 border rounded-lg">
										<div class="flex items-start gap-3">
											<div class="w-10 h-10 bg-gradient-to-br from-blue-500 to-purple-600 rounded-full flex items-center justify-center flex-shrink-0">
												<span class="text-white font-semibold text-sm">
													{member.name.split(' ').map(n => n[0]).join('')}
												</span>
											</div>
											<div class="flex-1">
												<h4 class="font-semibold">
													<a href={member.linkedin} target="_blank" class="hover:underline">
														{member.name}
													</a>
												</h4>
												<p class="text-sm font-medium text-blue-600 mb-1">{member.role}</p>
												<p class="text-sm text-muted-foreground">{member.description}</p>
											</div>
										</div>
									</div>
								{/each}
							</div>
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
								Ce projet m'a permis de développer un jeu illustrant un principe ergonomique numérique, en utilisant des 
								méthodes agiles et en collaborant avec une équipe de professionnels expérimentés. Cette expérience m'a aidé 
								à renforcer mes compétences en développement logiciel et en gestion de projet.
							</p>
							<p class="text-muted-foreground leading-relaxed">
								Le travail en autonomie dans un cadre structuré et la collaboration avec des experts du domaine ont été 
								des aspects particulièrement enrichissants de cette expérience professionnelle.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

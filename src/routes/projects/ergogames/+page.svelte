<script lang="ts">
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { ArrowLeft, Calendar, ExternalLink, Gamepad2, Lightbulb, Target } from '@lucide/svelte';
	import { Motion } from 'svelte-motion';
	import { onMount } from 'svelte';

	onMount(() => {
		if (typeof document !== 'undefined') {
			document.title = 'ErgoGames - Hugo Föllmi';
		}
	});

	const technologies = [
		{ name: 'Vue.js 3', color: '#4FC08D', url: 'https://vuejs.org/' },
		{
			name: 'JavaScript',
			color: '#F7DF1E',
			url: 'https://developer.mozilla.org/en-US/docs/Web/JavaScript'
		},
		{ name: 'Vuetify', color: '#1867C0', url: 'https://vuetifyjs.com/' },
		{ name: 'GitLab', color: '#FCA326', url: 'https://about.gitlab.com/' },
		{ name: 'Figma', color: '#F24E1E', url: 'https://www.figma.com/' },
		{ name: 'IntelliJ IDEA', color: '#000000', url: 'https://www.jetbrains.com/idea/' }
	];

	const deliverables = [
		{
			title: 'Jeu interactif "Au pas de course !"',
			type: 'professionnel'
		},
		{
			title: 'Page explicative du principe',
			type: 'professionnel'
		},
		{
			title: 'Documentation technique',
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
	<meta
		name="description"
		content="Développement du sixième jeu des ErgoGames 'Au pas de course !' chez Sogilis pour enseigner le principe ergonomique du groupement/proximité."
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
							ErgoGames - Au pas de course !
						</h1>
						<p class="mb-6 text-justify text-lg leading-relaxed text-muted-foreground">
							Développement du sixième jeu des
							<a
								href="https://www.ergogames.fr/"
								target="_blank"
								class="text-primary hover:underline"
							>
								ErgoGames
							</a>
							chez
							<a href="https://sogilis.com/" target="_blank" class="text-primary hover:underline">
								Sogilis
							</a>. Ce jeu a pour objectif de présenter le principe ergonomique du
							groupement/proximité de manière simple et ludique, avec une représentation visuelle
							interactive.
						</p>
						<div class="mb-6 flex flex-wrap gap-2">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								2e année de BUT
							</Badge>
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
								Principe ergonomique du web
							</Badge>
						</div>
					</div>
					<div class="flex w-full flex-col gap-4 lg:w-80">
						<a
							href="https://www.ergogames.fr/"
							target="_blank"
							class="group rounded-lg border p-4 transition-all hover:shadow-lg"
						>
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 items-center justify-center rounded-lg bg-gradient-to-br from-yellow-500 to-orange-600"
								>
									<span class="text-lg font-bold text-white">EG</span>
								</div>
								<div>
									<h3 class="font-semibold">ErgoGames</h3>
									<p class="text-sm text-muted-foreground">Site des ErgoGames</p>
								</div>
								<ExternalLink
									class="ml-auto h-4 w-4 opacity-0 transition-opacity group-hover:opacity-100"
								/>
							</div>
						</a>
						<a
							href="https://sogilis.com/"
							target="_blank"
							class="group rounded-lg border p-4 transition-all hover:shadow-lg"
						>
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 items-center justify-center rounded-lg bg-gradient-to-br from-blue-500 to-purple-600"
								>
									<span class="text-lg font-bold text-white">S</span>
								</div>
								<div>
									<h3 class="font-semibold">Sogilis</h3>
									<p class="text-sm text-muted-foreground">Entreprise de génie logiciel</p>
								</div>
								<ExternalLink
									class="ml-auto h-4 w-4 opacity-0 transition-opacity group-hover:opacity-100"
								/>
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
						<div class="grid grid-cols-1 gap-8 lg:grid-cols-2">
							<div>
								<h3 class="mb-4 text-xl font-semibold">Les ErgoGames</h3>
								<p class="mb-4 text-justify leading-relaxed text-muted-foreground">
									Le site des ErgoGames est conçu pour présenter de manière ludique les principes
									ergonomiques du numérique, tels que les actions minimales ou la gestion des
									erreurs. Il propose des jeux et un quiz pour faciliter l'apprentissage de ces
									principes.
								</p>
								<p class="text-justify leading-relaxed text-muted-foreground">
									Mon sujet de stage portait sur le développement du sixième jeu "Au pas de course
									!" qui illustre le principe ergonomique du groupement/proximité.
								</p>
							</div>
							<div>
								<h3 class="mb-4 text-xl font-semibold">Sogilis</h3>
								<p class="text-justify leading-relaxed text-muted-foreground">
									Entreprise de génie logiciel basée à Grenoble, spécialisée dans la création de
									solutions sur mesure de haute qualité pour divers secteurs industriels. Elle se
									distingue par ses valeurs fortes et son engagement envers la qualité, l'innovation
									et l'expérience utilisateur.
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
						<div class="grid grid-cols-1 gap-6 md:grid-cols-3">
							<div class="rounded-lg border p-4 text-center">
								<div
									class="mx-auto mb-3 flex h-12 w-12 items-center justify-center rounded-full bg-blue-100"
								>
									<Target class="h-6 w-6 text-blue-600" />
								</div>
								<h3 class="mb-2 font-semibold">Enseigner le principe</h3>
								<p class="text-sm text-muted-foreground">
									Développer un jeu interactif pour enseigner le principe ergonomique du
									groupement/proximité.
								</p>
							</div>
							<div class="rounded-lg border p-4 text-center">
								<div
									class="mx-auto mb-3 flex h-12 w-12 items-center justify-center rounded-full bg-green-100"
								>
									<Gamepad2 class="h-6 w-6 text-green-600" />
								</div>
								<h3 class="mb-2 font-semibold">Interface intuitive</h3>
								<p class="text-sm text-muted-foreground">
									Créer une interface utilisateur intuitive et accessible pour tous les niveaux de
									joueurs.
								</p>
							</div>
							<div class="rounded-lg border p-4 text-center">
								<div
									class="mx-auto mb-3 flex h-12 w-12 items-center justify-center rounded-full bg-purple-100"
								>
									<Lightbulb class="h-6 w-6 text-purple-600" />
								</div>
								<h3 class="mb-2 font-semibold">Page explicative</h3>
								<p class="text-sm text-muted-foreground">
									Développer une page dédiée à l'explication détaillée du principe ergonomique.
								</p>
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
						<div class="grid grid-cols-1 gap-4 md:grid-cols-2">
							{#each team as member}
								<div class="rounded-lg border p-4">
									<div class="flex items-start gap-3">
										<div
											class="flex h-10 w-10 flex-shrink-0 items-center justify-center rounded-full bg-gradient-to-br from-blue-500 to-purple-600"
										>
											<span class="text-sm font-semibold text-white">
												{member.name
													.split(' ')
													.map((n) => n[0])
													.join('')}
											</span>
										</div>
										<div class="flex-1">
											<h4 class="font-semibold">
												<a href={member.linkedin} target="_blank" class="hover:underline">
													{member.name}
												</a>
											</h4>
											<p class="mb-1 text-sm font-medium text-blue-600">{member.role}</p>
											<p class="text-sm text-muted-foreground">{member.description}</p>
										</div>
									</div>
								</div>
							{/each}
						</div>

						<div
							class="mt-6 rounded-lg border border-blue-200 bg-blue-50 p-4 dark:border-blue-500/30 dark:bg-blue-500/10"
						>
							<p class="text-sm text-muted-foreground">
								<span class="font-medium">Mon rôle :</span> Stagiaire développeur - J'ai développé le
								sixième jeu "Au pas de course !" en travaillant avec Vue.js 3 et Vuetify sous la supervision
								de l'équipe Sogilis.
							</p>
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
			transition={{ duration: 0.6, delay: 0.8 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Réalisations</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="mb-4 text-xl font-semibold">Le jeu "Au pas de course !"</h3>
							<p class="mb-6 leading-relaxed text-muted-foreground">
								Le jeu consiste à réaliser des courses dans des rayons de supermarchés, divisé en
								deux parties :
							</p>
							<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
								<div class="rounded-lg border p-4">
									<h4 class="mb-2 font-semibold text-blue-600">Première partie</h4>
									<p class="text-sm text-muted-foreground">
										Affichage aléatoire des produits dans les rayons
									</p>
								</div>
								<div class="rounded-lg border p-4">
									<h4 class="mb-2 font-semibold text-green-600">Deuxième partie</h4>
									<p class="text-sm text-muted-foreground">
										Affichage organisé selon le principe de groupement
									</p>
								</div>
							</div>
						</div>

						<div>
							<h3 class="mb-4 text-xl font-semibold">Livrables</h3>
							<div class="flex flex-wrap gap-4">
								{#each deliverables as deliverable}
									<div class="min-w-[250px] flex-1 rounded-lg border p-4">
										<div class="flex items-center gap-3">
											<div
												class="flex h-8 w-8 flex-shrink-0 items-center justify-center rounded-full {deliverable.type ===
												'professionnel'
													? 'bg-blue-100'
													: 'bg-green-100'}"
											>
												<span
													class="text-xs font-semibold {deliverable.type === 'professionnel'
														? 'text-blue-600'
														: 'text-green-600'}"
												>
													{deliverable.type === 'professionnel' ? 'P' : 'L'}
												</span>
											</div>
											<h4 class="font-semibold">{deliverable.title}</h4>
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
			transition={{ duration: 0.6, delay: 1.0 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Technologies utilisées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-2 gap-4 md:grid-cols-3 lg:grid-cols-6">
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

		<!-- Méthodologie -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 1.2 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Méthodologie</CardTitle>
					</CardHeader>
					<CardContent>
						<div>
							<h3 class="mb-4 text-xl font-semibold">Méthode SCRUM</h3>
							<p class="leading-relaxed text-muted-foreground">
								Le projet a été organisé en utilisant la méthode SCRUM, fonctionnant par cycles de
								deux semaines (sprints). Chaque sprint comprenait une réunion quotidienne (Daily)
								pour le suivi des tâches, ainsi qu'une réunion de fin de sprint combinant Sprint
								Review, Sprint Retrospective et Sprint Planning.
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
							<p class="leading-relaxed text-muted-foreground">
								Ce projet m'a permis de développer un jeu illustrant un principe ergonomique
								numérique, en utilisant des méthodes agiles et en collaborant avec une équipe de
								professionnels expérimentés. Cette expérience m'a aidé à renforcer mes compétences
								en développement logiciel et en gestion de projet.
							</p>
							<p class="leading-relaxed text-muted-foreground">
								Le travail en autonomie dans un cadre structuré et la collaboration avec des experts
								du domaine ont été des aspects particulièrement enrichissants.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

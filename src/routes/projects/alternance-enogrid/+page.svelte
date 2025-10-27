<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import {
		ExternalLink,
		Calendar,
		Users,
		Code,
		GitBranch,
		ArrowLeft,
		Zap
	} from '@lucide/svelte';

	const technologies = [
		{ name: 'React', color: '#61DAFB', url: 'https://react.dev/' },
		{ name: 'TypeScript', color: '#3178C6', url: 'https://www.typescriptlang.org/' },
		{ name: 'Excalidraw', color: '#000000', url: 'https://excalidraw.com/' },
		{ name: 'GitLab', color: '#FCA326', url: 'https://about.gitlab.com/' },
		{ name: 'Docker', color: '#2496ED', url: 'https://www.docker.com/' },
		{ name: 'Shadcn/ui', color: '#000000', url: 'https://ui.shadcn.com/' },
		{ name: 'Slack', color: '#4A154B', url: 'https://slack.com/' },
		{ name: 'Jira', color: '#0052CC', url: 'https://www.atlassian.com/software/jira' }
	];

	const achievements = [
		{
			title: 'Timeline interactive',
			description:
				"Développement d'une timeline pour guider les utilisateurs dans la création de projets d'autoconsommation collective"
		},
		{
			title: 'Gestion PMO',
			description: 'Interfaces pour la création et gestion de la Personne Morale Organisatrice'
		},
		{
			title: 'Génération de documents',
			description: "Système de création et envoi de contrats de vente et bulletins d'adhésion"
		},
		{
			title: 'Refonte UI/UX',
			description:
				"Refonte complète de l'application EnoConso avec shadcn/ui pour une meilleure expérience utilisateur"
		}
	];
</script>

<svelte:head>
	<title>Alternance Enogrid - Hugo Föllmi</title>
	<meta
		name="description"
		content="Découvrez mon alternance chez Enogrid, spécialisée dans la gestion de l'énergie et la transition énergétique."
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
							Alternance chez Enogrid
						</h1>
						<p class="mb-6 text-lg leading-relaxed text-muted-foreground text-justify">
							Au cours de mon alternance chez
							<a
								href="https://www.enogrid.com/"
								target="_blank"
								class="text-primary hover:underline"
							>
								Enogrid
							</a>, une entreprise spécialisée dans la gestion de l'énergie et la transition
							énergétique, j'ai eu l'occasion de travailler sur deux projets passionnants :
							<a
								href="https://monenergiecollective.fr/"
								target="_blank"
								class="text-primary hover:underline"
							>
								Mon Energie Collective
							</a>
							et
							<span class="text-primary"> EnoConso </span>.
						</p>
						<div class="mb-6 flex flex-wrap gap-2">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								3e année de BUT
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Users class="h-3 w-3" />
								Équipe technique
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Code class="h-3 w-3" />
								React & TypeScript
							</Badge>
						</div>
					</div>
					<div class="flex w-full flex-col gap-4 lg:w-80">
						<a
							href="https://www.enogrid.com/"
							target="_blank"
							class="group rounded-lg border p-4 transition-all hover:shadow-lg"
						>
							<div class="flex items-center gap-3">
								<Zap class="h-8 w-8 text-emerald-500" />
								<div>
									<h3 class="font-semibold">Enogrid</h3>
									<p class="text-sm text-muted-foreground">Transition énergétique</p>
								</div>
								<ExternalLink
									class="ml-auto h-4 w-4 opacity-0 transition-opacity group-hover:opacity-100"
								/>
							</div>
						</a>
						<a
							href="https://monenergiecollective.fr/"
							target="_blank"
							class="group rounded-lg border p-4 transition-all hover:shadow-lg"
						>
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 items-center justify-center rounded-lg bg-gradient-to-br from-emerald-500 to-teal-600"
								>
									<span class="text-lg font-bold text-white">MEC</span>
								</div>
								<div>
									<h3 class="font-semibold">Mon Energie Collective</h3>
									<p class="text-sm text-muted-foreground">Plateforme d'autoconsommation</p>
								</div>
								<ExternalLink
									class="ml-auto h-4 w-4 opacity-0 transition-opacity group-hover:opacity-100"
								/>
							</div>
						</a>
						<div class="rounded-lg border p-4">
							<div class="flex items-center gap-3">
								<div
									class="flex h-12 w-12 items-center justify-center rounded-lg bg-gradient-to-br from-blue-500 to-indigo-600"
								>
									<span class="text-lg font-bold text-white">EC</span>
								</div>
								<div>
									<h3 class="font-semibold">EnoConso</h3>
									<p class="text-sm text-muted-foreground">Suivi de consommation</p>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</Motion>

		<!-- Présentation Enogrid -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.2 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">À propos d'Enogrid</CardTitle>
					</CardHeader>
					<CardContent>
						<p class="leading-relaxed text-muted-foreground text-justify">
							Enogrid est une entreprise spécialisée dans la gestion de l'énergie et la transition
							énergétique. Fondée en 2018 par trois ingénieurs passionnés, cette start-up s'est
							construite autour d'une mission ambitieuse : démocratiser la transition énergétique
							à l'échelle locale. L'entreprise développe des solutions innovantes pour faciliter
							l'autoconsommation collective et le suivi de consommation énergétique.
						</p>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Méthodologie -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.3 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Méthodologie et équipe</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="mb-4 text-xl font-semibold">Méthode Agile Scrum</h3>
							<p class="mb-4 leading-relaxed text-muted-foreground text-justify">
								Chez Enogrid, nous utilisons une méthode Agile basée sur le framework Scrum avec des
								cycles de deux semaines (sprints), des réunions quotidiennes (Daily Stand-up), des
								"Features Lunch" (Sprint Planning) et des rétrospectives mensuelles.
							</p>
							<div class="grid grid-cols-1 gap-4 md:grid-cols-2">
								<div class="rounded-lg border p-4">
									<h4 class="mb-2 flex items-center gap-2 font-semibold">
										<Users class="h-4 w-4" />
										Équipe technique
									</h4>
									<ul class="space-y-1 text-sm text-muted-foreground">
										<li>
											•
											<a
												href="https://www.linkedin.com/in/thomas-gaillot/"
												target="_blank"
												class="text-primary hover:underline"
											>
												Thomas Gaillot
											</a>
											- Tuteur & Développeur front-end
										</li>
										<li>• Product Owner - Définition des sprints</li>
										<li>• Testeurs - Validation des fonctionnalités</li>
										<li>• Développeurs Back-end - Intégration</li>
									</ul>
								</div>
								<div class="rounded-lg border p-4">
									<h4 class="mb-2 flex items-center gap-2 font-semibold">
										<GitBranch class="h-4 w-4" />
										Processus de développement
									</h4>
									<ul class="space-y-1 text-sm text-muted-foreground">
										<li>
											• Maquettes sur
											<a
												href="https://excalidraw.com/"
												target="_blank"
												class="text-primary hover:underline"
											>
												Excalidraw
											</a>
										</li>
										<li>• POC en local</li>
										<li>• Intégration back-end</li>
										<li>• Tests sur Kraken</li>
										<li>• Beta-tests utilisateurs</li>
									</ul>
								</div>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Projet 1: Mon Energie Collective -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.4 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Semestre 1 : Mon Energie Collective</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="mb-4 text-xl font-semibold">Contexte</h3>
							<p class="leading-relaxed text-muted-foreground text-justify">
								Mon Energie Collective est une plateforme centrale pour la mise en œuvre
								opérationnelle des projets d'autoconsommation collective. Cet outil accompagne
								l'ensemble du processus, depuis la création de la Personne Morale Organisatrice
								(PMO) jusqu'au recrutement des bénéficiaires.
							</p>
						</div>

						<div>
							<h3 class="mb-4 text-xl font-semibold">Objectifs</h3>
							<p class="leading-relaxed text-muted-foreground text-justify">
								Mon objectif principal était de m'intégrer dans l'équipe technique et de comprendre
								le fonctionnement d'un projet d'entreprise réel. Les sprints tournaient autour de
								l'ajout de la gestion de la création d'un projet depuis le début, incluant
								l'intégration d'une timeline interactive et le développement d'interfaces pour la
								PMO.
							</p>
						</div>

						<div>
							<h3 class="mb-4 text-xl font-semibold">Réalisations</h3>
							<div class="grid grid-cols-1 gap-4 md:grid-cols-2">
								{#each achievements.slice(0, 3) as achievement}
									<div class="rounded-lg border p-4">
										<h4 class="mb-2 font-semibold">{achievement.title}</h4>
										<p class="text-sm text-muted-foreground">{achievement.description}</p>
									</div>
								{/each}
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<!-- Projet 2: EnoConso -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.5 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Semestre 2: EnoConso</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="mb-4 text-xl font-semibold">Contexte</h3>
							<p class="leading-relaxed text-muted-foreground text-justify">
								EnoConso regroupe sur une application web les différents éléments du projet pour
								tous les participants. L'application donne accès à la consommation d'énergie et son
								historique, présente des éléments administratifs comme les factures, et permet la
								communication entre participants, producteurs et support Enogrid.
							</p>
						</div>

						<div>
							<h3 class="mb-4 text-xl font-semibold">Objectifs</h3>
							<p class="leading-relaxed text-muted-foreground text-justify">
								Travailler en autonomie sur un produit existant pour le rendre plus utilisable et
								plus intuitif pour les utilisateurs, en réalisant des modifications en profondeur.
							</p>
						</div>

						<div>
							<h3 class="mb-4 text-xl font-semibold">Réalisations</h3>
							<div class="rounded-lg border p-4">
								<h4 class="mb-2 font-semibold">Refonte UI/UX complète</h4>
								<p class="text-sm text-muted-foreground text-justify">
									Refonte des couleurs et de l'interface pour l'accorder avec la charte graphique de
									Mon Energie Collective, en utilisant la librairie shadcn/ui pour une expérience
									utilisateur moderne et cohérente.
								</p>
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
			transition={{ duration: 0.6, delay: 0.6 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Technologies utilisées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-2 gap-4 md:grid-cols-3 lg:grid-cols-4">
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

		<!-- Bilan -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 1.0 }}
		>
			<div use:motion>
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Bilan de l'expérience</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="space-y-4">
							<p class="leading-relaxed text-muted-foreground text-justify">
								Cette alternance m'a permis de développer mes compétences en React et TypeScript,
								des technologies que je ne maîtrisais pas auparavant. J'ai appris à travailler en
								équipe sur un projet d'entreprise avec des enjeux réels, ce qui diffère
								significativement des projets académiques.
							</p>
							<p class="leading-relaxed text-muted-foreground text-justify">
								L'environnement de travail est stimulant et propice à l'apprentissage. Cette
								dynamique me motive profondément à contribuer activement au projet, avec l'objectif
								d'aider un maximum d'utilisateurs à bénéficier des solutions innovantes proposées
								par l'entreprise dans le domaine de la transition énergétique.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

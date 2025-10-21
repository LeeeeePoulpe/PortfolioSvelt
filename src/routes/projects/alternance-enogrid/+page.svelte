<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { ExternalLink, Calendar, Users, Code, Database, GitBranch } from '@lucide/svelte';

	const technologies = [
		{ name: 'React', color: '#61DAFB' },
		{ name: 'TypeScript', color: '#3178C6' },
		{ name: 'Excalidraw', color: '#000000' },
		{ name: 'GitLab', color: '#FCA326' },
		{ name: 'Docker', color: '#2496ED' },
		{ name: 'Shadcn/ui', color: '#000000' },
		{ name: 'Slack', color: '#4A154B' },
		{ name: 'Jira', color: '#0052CC' }
	];

	const achievements = [
		{
			title: 'Timeline interactive',
			description: "Développement d'une timeline pour guider les utilisateurs dans la création de projets d'autoconsommation collective"
		},
		{
			title: 'Gestion PMO',
			description: 'Interfaces pour la création et gestion de la Personne Morale Organisatrice'
		},
		{
			title: 'Génération de documents',
			description: 'Système de création et envoi de contrats de vente et bulletins d\'adhésion'
		},
		{
			title: 'Refonte UI/UX',
			description: "Refonte complète de l'application EnoConso avec shadcn/ui pour une meilleure expérience utilisateur"
		}
	];
</script>

<svelte:head>
	<title>Alternance Enogrid - Hugo Föllmi</title>
	<meta name="description" content="Découvrez mon alternance chez Enogrid, spécialisée dans la gestion de l'énergie et la transition énergétique." />
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
							Alternance chez Enogrid
						</h1>
						<p class="text-lg leading-relaxed text-muted-foreground mb-6">
							Au cours de mon alternance chez 
							<a href="https://www.enogrid.com/" target="_blank" class="text-primary hover:underline">
								Enogrid
							</a>, 
							une entreprise spécialisée dans la gestion de l'énergie et la transition énergétique, 
							j'ai eu l'occasion de travailler sur deux projets passionnants : 
							<a href="https://monenergiecollective.fr/" target="_blank" class="text-primary hover:underline">
								Mon Energie Collective
							</a> 
							et 
							<span class="text-primary">
								EnoConso
							</span>.
						</p>
						<div class="flex flex-wrap gap-2 mb-6">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								Septembre 2024 - En cours
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
					<div class="flex flex-col gap-4 w-full lg:w-80">
						<a
							href="https://monenergiecollective.fr/"
							target="_blank"
							class="group p-4 border rounded-lg hover:shadow-lg transition-all"
						>
							<div class="flex items-center gap-3">
								<div class="w-12 h-12 bg-gradient-to-br from-emerald-500 to-teal-600 rounded-lg flex items-center justify-center">
									<span class="text-white font-bold text-lg">MEC</span>
								</div>
								<div>
									<h3 class="font-semibold">Mon Energie Collective</h3>
									<p class="text-sm text-muted-foreground">Plateforme d'autoconsommation</p>
								</div>
								<ExternalLink class="h-4 w-4 ml-auto opacity-0 group-hover:opacity-100 transition-opacity" />
							</div>
						</a>
						<a
							href="https://enoconso.fr/"
							target="_blank"
							class="group p-4 border rounded-lg hover:shadow-lg transition-all"
						>
							<div class="flex items-center gap-3">
								<div class="w-12 h-12 bg-gradient-to-br from-blue-500 to-indigo-600 rounded-lg flex items-center justify-center">
									<span class="text-white font-bold text-lg">EC</span>
								</div>
								<div>
									<h3 class="font-semibold">EnoConso</h3>
									<p class="text-sm text-muted-foreground">Suivi de consommation</p>
								</div>
								<ExternalLink class="h-4 w-4 ml-auto opacity-0 group-hover:opacity-100 transition-opacity" />
							</div>
						</a>
					</div>
				</div>
			</div>
		</Motion>

		<!-- Projet 1: Mon Energie Collective -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.2 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Semestre 1: Mon Energie Collective</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="text-xl font-semibold mb-4">Contexte</h3>
							<p class="text-muted-foreground leading-relaxed">
								Enogrid est une entreprise spécialisée dans la gestion de l'énergie et la transition énergétique. 
								Fondée en 2018 par trois ingénieurs passionnés, cette start-up s'est construite autour d'une mission 
								ambitieuse : démocratiser la transition énergétique à l'échelle locale.
							</p>
							<p class="text-muted-foreground leading-relaxed mt-4">
								Mon Energie Collective est une plateforme centrale pour la mise en œuvre opérationnelle des projets 
								d'autoconsommation collective. Cet outil accompagne l'ensemble du processus, depuis la création de la 
								Personne Morale Organisatrice (PMO) jusqu'au recrutement des bénéficiaires.
							</p>
						</div>

						<div>
							<h3 class="text-xl font-semibold mb-4">Objectifs</h3>
							<p class="text-muted-foreground leading-relaxed">
								Mon objectif principal était de m'intégrer dans l'équipe technique et de comprendre le fonctionnement 
								d'un projet d'entreprise réel. Les sprints tournaient autour de l'ajout de la gestion de la création 
								d'un projet depuis le début, incluant l'intégration d'une timeline interactive et le développement 
								d'interfaces pour la PMO.
							</p>
						</div>

						<div>
							<h3 class="text-xl font-semibold mb-4">Réalisations</h3>
							<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
								{#each achievements.slice(0, 3) as achievement}
									<div class="p-4 border rounded-lg">
										<h4 class="font-semibold mb-2">{achievement.title}</h4>
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
			transition={{ duration: 0.6, delay: 0.4 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Semestre 2: EnoConso</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="text-xl font-semibold mb-4">Contexte</h3>
							<p class="text-muted-foreground leading-relaxed">
								EnoConso regroupe sur une application web les différents éléments du projet pour tous les participants. 
								L'application donne accès à la consommation d'énergie et son historique, présente des éléments 
								administratifs comme les factures, et permet la communication entre participants, producteurs et support Enogrid.
							</p>
						</div>

						<div>
							<h3 class="text-xl font-semibold mb-4">Objectifs</h3>
							<p class="text-muted-foreground leading-relaxed">
								Travailler en autonomie sur un produit existant pour le rendre plus utilisable et plus intuitif 
								pour les utilisateurs, en réalisant des modifications en profondeur.
							</p>
						</div>

						<div>
							<h3 class="text-xl font-semibold mb-4">Réalisations</h3>
							<div class="p-4 border rounded-lg">
								<h4 class="font-semibold mb-2">Refonte UI/UX complète</h4>
								<p class="text-sm text-muted-foreground">
									Refonte des couleurs et de l'interface pour l'accorder avec la charte graphique de Mon Energie Collective, 
									en utilisant la librairie shadcn/ui pour une expérience utilisateur moderne et cohérente.
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
						<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
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

		<!-- Méthodologie -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.8 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Méthodologie et équipe</CardTitle>
					</CardHeader>
					<CardContent class="space-y-6">
						<div>
							<h3 class="text-xl font-semibold mb-4">Méthode Agile Scrum</h3>
							<p class="text-muted-foreground leading-relaxed mb-4">
								Chez Enogrid, nous utilisons une méthode Agile basée sur le framework Scrum avec des cycles de deux semaines (sprints), 
								des réunions quotidiennes (Daily Stand-up), des "Features Lunch" (Sprint Planning) et des rétrospectives mensuelles.
							</p>
							<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
								<div class="p-4 border rounded-lg">
									<h4 class="font-semibold mb-2 flex items-center gap-2">
										<Users class="h-4 w-4" />
										Équipe technique
									</h4>
									<ul class="text-sm text-muted-foreground space-y-1">
										<li>• Thomas Gaillot - Tuteur & Développeur front-end</li>
										<li>• Product Owner - Définition des sprints</li>
										<li>• Testeurs - Validation des fonctionnalités</li>
										<li>• Développeurs Back-end - Intégration</li>
									</ul>
								</div>
								<div class="p-4 border rounded-lg">
									<h4 class="font-semibold mb-2 flex items-center gap-2">
										<GitBranch class="h-4 w-4" />
										Processus de développement
									</h4>
									<ul class="text-sm text-muted-foreground space-y-1">
										<li>• Maquettes sur Excalidraw</li>
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
							<p class="text-muted-foreground leading-relaxed">
								Cette alternance m'a permis de développer mes compétences en React et TypeScript, des technologies 
								que je ne maîtrisais pas auparavant. J'ai appris à travailler en équipe sur un projet d'entreprise 
								avec des enjeux réels, ce qui diffère significativement des projets académiques.
							</p>
							<p class="text-muted-foreground leading-relaxed">
								L'environnement de travail est stimulant et propice à l'apprentissage. Cette dynamique me motive 
								profondément à contribuer activement au projet, avec l'objectif d'aider un maximum d'utilisateurs 
								à bénéficier des solutions innovantes proposées par l'entreprise dans le domaine de la transition énergétique.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

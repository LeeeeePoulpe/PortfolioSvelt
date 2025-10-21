<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Calendar, Users, Smartphone, Monitor, GitBranch, CheckCircle } from '@lucide/svelte';

	const technologies = [
		{ name: 'Android', color: '#3DDC84' },
		{ name: 'Java', color: '#007396' },
		{ name: 'MySQL', color: '#4479A1' },
		{ name: 'Docker', color: '#2496ED' },
		{ name: 'Git', color: '#F05032' }
	];

	const improvements = [
		{
			title: 'Optimisation du cycle de vie',
			description: 'Réduction des appels API et amélioration des initialisations pour de meilleures performances'
		},
		{
			title: 'Interface utilisateur intuitive',
			description: 'Ajout de Toasts pour des retours immédiats et navigation simplifiée'
		},
		{
			title: 'Client web amélioré',
			description: 'Mise en avant des boutons d\'accès au tableau de bord et indicateurs visuels pour administrateurs'
		},
		{
			title: 'Fonctionnalité d\'importation',
			description: 'Ajout d\'une fonctionnalité d\'importation des offres de stage'
		}
	];

	const problems = [
		'Problèmes de connexion et de chargement des offres de stage',
		'Interface Android vraiment inutilisable',
		'Duplicata de code dans le serveur',
		'Ergonomie du site web à améliorer'
	];
</script>

<svelte:head>
	<title>Carnet de Stage - Hugo Föllmi</title>
	<meta name="description" content="Projet de réparation et amélioration de l'application Android et du site web du carnet de stage de l'IUT2 de Grenoble." />
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
							Carnet de Stage IUT2
						</h1>
						<p class="text-lg leading-relaxed text-muted-foreground mb-6">
							Projet de réparation et amélioration de l'application Android et du site web du carnet de stage 
							de l'IUT2 de Grenoble. Ce projet a été réalisé dans le cadre de la formation BUT Informatique 
							lors du quatrième semestre, en équipe de 6 personnes.
						</p>
						<div class="flex flex-wrap gap-2 mb-6">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								5 jours de travail
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Users class="h-3 w-3" />
								Équipe de 6
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Smartphone class="h-3 w-3" />
								Android & Web
							</Badge>
						</div>
					</div>
					<div class="flex flex-col gap-4 w-full lg:w-80">
						<div class="p-4 border rounded-lg">
							<div class="flex items-center gap-3 mb-3">
								<Smartphone class="h-8 w-8 text-green-500" />
								<div>
									<h3 class="font-semibold">Application Android</h3>
									<p class="text-sm text-muted-foreground">Carnet de stage mobile</p>
								</div>
							</div>
							<p class="text-sm text-muted-foreground">
								Application pour trouver les offres de stage, postuler et suivre l'avancement de la recherche.
							</p>
						</div>
						<div class="p-4 border rounded-lg">
							<div class="flex items-center gap-3 mb-3">
								<Monitor class="h-8 w-8 text-blue-500" />
								<div>
									<h3 class="font-semibold">Site Web</h3>
									<p class="text-sm text-muted-foreground">Interface web complémentaire</p>
								</div>
							</div>
							<p class="text-sm text-muted-foreground">
								Plateforme web pour la gestion des offres et le suivi des candidatures.
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
								<h3 class="text-xl font-semibold mb-4">Organisation temporelle</h3>
								<div class="space-y-3">
									<div class="flex items-center gap-3 p-3 border rounded-lg">
										<div class="w-8 h-8 bg-blue-100 rounded-full flex items-center justify-center">
											<span class="text-blue-600 font-semibold text-sm">1-2</span>
										</div>
										<div>
											<h4 class="font-medium">Jours 1-2 : Maquettage</h4>
											<p class="text-sm text-muted-foreground">Amélioration de l'ergonomie des parties web et Android</p>
										</div>
									</div>
									<div class="flex items-center gap-3 p-3 border rounded-lg">
										<div class="w-8 h-8 bg-green-100 rounded-full flex items-center justify-center">
											<span class="text-green-600 font-semibold text-sm">3-5</span>
										</div>
										<div>
											<h4 class="font-medium">Jours 3-5 : Développement</h4>
											<p class="text-sm text-muted-foreground">Réparation du site web et de l'application Android</p>
										</div>
									</div>
								</div>
							</div>
							<div>
								<h3 class="text-xl font-semibold mb-4">Problèmes identifiés</h3>
								<div class="space-y-2">
									{#each problems as problem}
										<div class="flex items-start gap-2">
											<div class="w-2 h-2 bg-red-500 rounded-full mt-2 flex-shrink-0"></div>
											<p class="text-sm text-muted-foreground">{problem}</p>
										</div>
									{/each}
								</div>
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
									<CheckCircle class="h-6 w-6 text-blue-600" />
								</div>
								<h3 class="font-semibold mb-2">Améliorer l'ergonomie</h3>
								<p class="text-sm text-muted-foreground">
									Proposer des améliorations ergonomiques à travers des maquettes pour les interfaces web et Android.
								</p>
							</div>
							<div class="text-center p-4 border rounded-lg">
								<div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-3">
									<GitBranch class="h-6 w-6 text-green-600" />
								</div>
								<h3 class="font-semibold mb-2">Réparer les bugs</h3>
								<p class="text-sm text-muted-foreground">
									Corriger les problèmes de connexion et de chargement des offres de stage.
								</p>
							</div>
							<div class="text-center p-4 border rounded-lg">
								<div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mx-auto mb-3">
									<Users class="h-6 w-6 text-purple-600" />
								</div>
								<h3 class="font-semibold mb-2">Ajouter des fonctionnalités</h3>
								<p class="text-sm text-muted-foreground">
									Développer de nouvelles fonctionnalités pour améliorer l'expérience utilisateur.
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
						<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
							{#each improvements as improvement}
								<div class="p-4 border rounded-lg hover:shadow-md transition-shadow">
									<h4 class="font-semibold mb-2 flex items-center gap-2">
										<CheckCircle class="h-4 w-4 text-green-500" />
										{improvement.title}
									</h4>
									<p class="text-sm text-muted-foreground">{improvement.description}</p>
								</div>
							{/each}
						</div>
						
						<div class="mt-8 p-6 bg-gradient-to-r from-blue-50 to-indigo-50 rounded-lg">
							<h4 class="font-semibold mb-3">Résultat final</h4>
							<p class="text-muted-foreground">
								Nous avons livré une application plus performante et plus conviviale, prête à répondre aux besoins 
								des utilisateurs. L'optimisation du cycle de vie de l'application Android et la refonte de l'interface 
								utilisateur du client web ont considérablement amélioré l'expérience utilisateur.
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
			transition={{ duration: 0.6, delay: 0.8 }}
		>
			<div use:motion class="mb-16">
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Technologies utilisées</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-4">
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
			transition={{ duration: 0.6, delay: 1.0 }}
		>
			<div use:motion>
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Conclusion</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="space-y-4">
							<p class="text-muted-foreground leading-relaxed">
								Ce projet nous a permis d'améliorer nos compétences techniques en optimisant le cycle de vie de l'application 
								Android et en repensant l'interface utilisateur du client web. Nous avons renforcé notre capacité à travailler 
								en équipe et à résoudre des problèmes techniques complexes.
							</p>
							<p class="text-muted-foreground leading-relaxed">
								L'intervention sur un code existant pour le réparer et l'améliorer a été une expérience formatrice qui nous a 
								permis de comprendre l'importance de la maintenance et de l'optimisation dans le développement logiciel.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

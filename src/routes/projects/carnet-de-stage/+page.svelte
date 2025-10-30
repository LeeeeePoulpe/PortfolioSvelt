<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Button } from '$lib/components/ui/button/index.js';
	import {
		Calendar,
		Users,
		Smartphone,
		Monitor,
		Code,
		CheckCircle,
		ArrowLeft,
		Lightbulb
	} from '@lucide/svelte';

	const technologies = [
		{ name: 'Android', color: '#3DDC84', url: 'https://developer.android.com/' },
		{ name: 'Java', color: '#007396', url: 'https://www.java.com/' },
		{ name: 'Symfony', color: '#000000', url: 'https://symfony.com/' },
		{ name: 'MySQL', color: '#4479A1', url: 'https://www.mysql.com/' },
		{ name: 'Docker', color: '#2496ED', url: 'https://www.docker.com/' }
	];

	const projectSteps = [
		{
			step: '1-2',
			title: 'Maquettage',
			description: "Amélioration de l'ergonomie des parties web et Android",
			icon: Lightbulb
		},
		{
			step: '3-5',
			title: 'Développement',
			description: "Réparation du site web et de l'application Android",
			icon: Code
		}
	];

	const problems = [
		'Problèmes de connexion et de chargement des offres de stage',
		'Interface Android vraiment inutilisable',
		'Duplicata de code dans le serveur',
		'Ergonomie du site web à améliorer'
	];

	const improvements = [
		{
			title: 'Optimisation du cycle de vie',
			description:
				'Réduction des appels API et amélioration des initialisations pour de meilleures performances'
		},
		{
			title: 'Configuration Docker',
			description: 'Ajustement du code serveur avec Docker pour faciliter les tests'
		},
		{
			title: 'Interface utilisateur intuitive',
			description: 'Ajout de Toasts pour des retours immédiats et navigation simplifiée'
		},
		{
			title: 'Client web amélioré',
			description:
				"Mise en avant des boutons d'accès au tableau de bord et indicateurs visuels pour administrateurs"
		},
		{
			title: "Fonctionnalité d'importation",
			description: "Ajout d'une fonctionnalité d'importation des offres de stage"
		}
	];
</script>

<svelte:head>
	<title>Carnet de Stage - Hugo Föllmi</title>
	<meta
		name="description"
		content="Projet de réparation et amélioration de l'application Android et du site web du carnet de stage de l'IUT2 de Grenoble."
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
							Carnet de Stage IUT2
						</h1>
						<p class="mb-6 text-justify text-lg leading-relaxed text-muted-foreground">
							Projet de réparation et amélioration de l'application Android et du site web du carnet
							de stage de l'IUT2 de Grenoble. Cette application permet aux étudiants de trouver les
							offres de stage, de postuler à ces offres et de suivre l'avancement de leur recherche.
							Projet réalisé dans le cadre du BUT Informatique lors du quatrième semestre, en équipe
							de 6 personnes.
						</p>
						<div class="mb-6 flex flex-wrap gap-2">
							<Badge variant="secondary" class="flex items-center gap-1">
								<Calendar class="h-3 w-3" />
								2e année de BUT
							</Badge>
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
								Android
							</Badge>
							<Badge variant="secondary" class="flex items-center gap-1">
								<Monitor class="h-3 w-3" />
								Web
							</Badge>
						</div>
					</div>
					<div class="flex w-full flex-col gap-4 lg:w-80">
						<div class="rounded-lg border p-4">
							<div class="mb-3 flex items-center gap-3">
								<Smartphone class="h-8 w-8 text-green-500" />
								<div>
									<h3 class="font-semibold">Application Android</h3>
									<p class="text-sm text-muted-foreground">Carnet de stage mobile</p>
								</div>
							</div>
							<p class="text-justify text-sm text-muted-foreground">
								Application pour trouver les offres de stage, postuler et suivre l'avancement de la
								recherche.
							</p>
						</div>
						<div class="rounded-lg border p-4">
							<div class="mb-3 flex items-center gap-3">
								<Monitor class="h-8 w-8 text-blue-500" />
								<div>
									<h3 class="font-semibold">Site Web (Symfony)</h3>
									<p class="text-sm text-muted-foreground">Interface web complémentaire</p>
								</div>
							</div>
							<p class="text-justify text-sm text-muted-foreground">
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
						<div class="grid grid-cols-1 gap-8 lg:grid-cols-2">
							<div>
								<h3 class="mb-4 text-xl font-semibold">Cadre du projet</h3>
								<p class="mb-4 text-justify leading-relaxed text-muted-foreground">
									Projet réalisé dans le cadre du BUT Informatique à l'IUT2 de Grenoble lors du
									quatrième semestre. L'objectif était de réparer et d'améliorer une application
									Android et un site web existants permettant aux étudiants de gérer leurs
									recherches de stage.
								</p>
							</div>
							<div>
								<h3 class="mb-4 text-xl font-semibold">Problèmes identifiés</h3>
								<p class="mb-3 text-justify leading-relaxed text-muted-foreground">
									Analyse de l'existant révélant des défauts majeurs : l'application Android était
									inutilisable et le site web présentait de nombreux duplicata de code rendant la
									maintenance difficile.
								</p>
								<div class="space-y-2">
									{#each problems as problem}
										<div class="flex items-start gap-2">
											<div class="mt-2 h-2 w-2 flex-shrink-0 rounded-full bg-red-500"></div>
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

		<!-- Étapes du développement -->
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
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
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
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
							<div class="rounded-lg border p-4">
								<div class="mb-3 flex items-center gap-3">
									<Smartphone class="h-6 w-6 text-green-500" />
									<h4 class="font-semibold">Développeurs Android</h4>
								</div>
								<p class="text-sm text-muted-foreground">
									2 développeurs concentrés sur l'amélioration de l'application mobile
								</p>
							</div>
							<div class="rounded-lg border p-4">
								<div class="mb-3 flex items-center gap-3">
									<Monitor class="h-6 w-6 text-blue-500" />
									<h4 class="font-semibold">Développeurs Web (Symfony)</h4>
								</div>
								<p class="text-sm text-muted-foreground">
									4 développeurs dédiés au développement et à l'amélioration de la plateforme web
								</p>
							</div>
						</div>

						<div
							class="mt-6 rounded-lg border border-green-200 bg-green-50 p-4 dark:border-green-500/30 dark:bg-green-500/10"
						>
							<p class="text-justify text-sm text-muted-foreground">
								<span class="font-medium">Mon rôle :</span> Développeur Android - J'ai travaillé sur
								l'amélioration de l'application mobile, en optimisant le cycle de vie, en corrigeant
								des bugs tout en ajoutant de nouvelles fonctionnalités pour améliorer l'expérience utilisateur.
							</p>
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
						<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
							{#each improvements as improvement}
								<div class="rounded-lg border p-4 transition-shadow hover:shadow-md">
									<h4 class="mb-2 flex items-center gap-2 font-semibold">
										<CheckCircle class="h-4 w-4 text-green-500" />
										{improvement.title}
									</h4>
									<p class="text-sm text-muted-foreground">{improvement.description}</p>
								</div>
							{/each}
						</div>
						<div
							class="rounded-lg bg-gradient-to-r from-green-50 to-blue-50 p-4 dark:from-green-500/10 dark:to-blue-500/10"
						>
							<p class="text-justify text-sm text-muted-foreground">
								Nous avons livré une application plus performante et plus conviviale, prête à
								répondre aux besoins des utilisateurs. L'application Android est désormais
								utilisable et le site web est mieux organisé et plus maintenable.
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
			transition={{ duration: 0.6, delay: 0.7 }}
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
			transition={{ duration: 0.6, delay: 0.8 }}
		>
			<div use:motion>
				<Card>
					<CardHeader>
						<CardTitle class="text-2xl">Conclusion</CardTitle>
					</CardHeader>
					<CardContent>
						<div class="space-y-4">
							<p class="text-justify leading-relaxed text-muted-foreground">
								Ce projet nous a permis d'améliorer nos compétences techniques en optimisant le
								cycle de vie de l'application Android et en repensant l'interface utilisateur du
								client web. Nous avons renforcé notre capacité à travailler en équipe et à résoudre
								des problèmes techniques complexes.
							</p>
							<p class="text-justify leading-relaxed text-muted-foreground">
								L'intervention sur un code existant pour le réparer et l'améliorer a été une
								expérience formatrice qui nous a permis de comprendre l'importance de la maintenance
								et de l'optimisation dans le développement logiciel.
							</p>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>
	</div>
</main>

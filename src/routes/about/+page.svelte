<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent } from '$lib/components/ui/card/index.js';
	import { Code2, Palette, Rocket, Users } from '@lucide/svelte';

	// Langages
	import IconJava from '~icons/devicon/java';
	import IconPython from '~icons/devicon/python';
	import IconJavascript from '~icons/devicon/javascript';
	import IconTypescript from '~icons/devicon/typescript';
	import IconNodejs from '~icons/devicon/nodejs';
	import IconPhp from '~icons/devicon/php';
	import IconMysql from '~icons/devicon/mysql';

	// Frameworks
	import IconSymfony from '~icons/devicon/symfony';
	import IconReact from '~icons/devicon/react';
	import IconNextjs from '~icons/devicon/nextjs';
	import IconAndroid from '~icons/devicon/android';

	// Outils
	import IconGit from '~icons/devicon/git';
	import IconDocker from '~icons/devicon/docker';
	import IconPostgresql from '~icons/devicon/postgresql';
	import IconMongodb from '~icons/devicon/mongodb';
	import IconFigma from '~icons/devicon/figma';

	type Skill = {
		name: string;
		icon: any;
		color: string;
		url: string;
	};

	const languages: Skill[] = [
		{ name: 'Java', icon: IconJava, color: '#007396', url: 'https://www.java.com' },
		{ name: 'Python', icon: IconPython, color: '#3776AB', url: 'https://www.python.org' },
		{
			name: 'JavaScript',
			icon: IconJavascript,
			color: '#F7DF1E',
			url: 'https://developer.mozilla.org/en-US/docs/Web/JavaScript'
		},
		{
			name: 'TypeScript',
			icon: IconTypescript,
			color: '#3178C6',
			url: 'https://www.typescriptlang.org'
		},
		{ name: 'PHP', icon: IconPhp, color: '#777BB4', url: 'https://www.php.net' },
		{ name: 'SQL', icon: IconMysql, color: '#4479A1', url: 'https://www.mysql.com' }
	];

	const frameworks: Skill[] = [
		{ name: 'Symfony', icon: IconSymfony, color: '#000000', url: 'https://symfony.com' },
		{ name: 'React', icon: IconReact, color: '#61DAFB', url: 'https://react.dev' },
		{ name: 'Next.js', icon: IconNextjs, color: '#000000', url: 'https://nextjs.org' },
		{ name: 'Node.js', icon: IconNodejs, color: '#339933', url: 'https://nodejs.org' },
		{ name: 'Android', icon: IconAndroid, color: '#3DDC84', url: 'https://developer.android.com' }
	];

	const tools: Skill[] = [
		{ name: 'Git', icon: IconGit, color: '#F05032', url: 'https://git-scm.com' },
		{ name: 'Docker', icon: IconDocker, color: '#2496ED', url: 'https://www.docker.com' },
		{
			name: 'PostgreSQL',
			icon: IconPostgresql,
			color: '#4169E1',
			url: 'https://www.postgresql.org'
		},
		{ name: 'MongoDB', icon: IconMongodb, color: '#47A248', url: 'https://www.mongodb.com' },
		{ name: 'Figma', icon: IconFigma, color: '#F24E1E', url: 'https://www.figma.com' }
	];

	const values = [
		{
			icon: Code2,
			title: 'Code de qualité',
			description: 'Je privilégie les bonnes pratiques et un code maintenable'
		},
		{
			icon: Palette,
			title: 'Design moderne',
			description: 'Des interfaces élégantes et intuitives pour une meilleure UX'
		},
		{
			icon: Rocket,
			title: 'Performance',
			description: 'Optimisation et rapidité au cœur de mes développements'
		},
		{
			icon: Users,
			title: 'Collaboration',
			description: "Travail d'équipe et communication efficace"
		}
	];
</script>

<main class="min-h-screen pt-32 pb-16">
	<div class="mx-auto max-w-5xl px-4 sm:px-6 lg:px-8">
		<!-- Introduction Section -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6 }}
		>
			<div use:motion>
				<h1 class="font-display mb-6 text-4xl font-bold text-foreground sm:text-5xl">
					À propos de moi
				</h1>
				<div class="prose prose-lg max-w-none">
					<p class="mb-6 text-lg leading-relaxed text-muted-foreground">
						Je m'appelle Hugo Föllmi, j'ai 19 ans et je suis né le 11 novembre 2004 à Santiago du
						Chili. Actuellement étudiant, je suis passionné par le développement informatique et la
						création d'applications innovantes.
					</p>
					<p class="mb-6 text-lg leading-relaxed text-muted-foreground">
						Mon parcours m'a permis d'acquérir des compétences variées en développement web et
						mobile, de la conception à la mise en production. J'aime relever des défis techniques et
						apprendre de nouvelles technologies pour créer des solutions efficaces et élégantes.
					</p>
				</div>
			</div>
		</Motion>
	</div>

	<!-- Languages Carousel -->
	<Motion
		let:motion
		initial={{ opacity: 0, y: 20 }}
		animate={{ opacity: 1, y: 0 }}
		transition={{ duration: 0.6, delay: 0.2 }}
	>
		<div use:motion class="mt-12">
			<div
				class="relative -mx-4 overflow-hidden border-y border-border bg-card/30 py-8 backdrop-blur-md sm:-mx-6 lg:-mx-8"
			>
				<div class="animate-scroll flex flex-row flex-nowrap gap-12 px-8">
					{#each [...languages, ...languages, ...languages, ...languages] as skill}
						<a
							href={skill.url}
							target="_blank"
							rel="noopener noreferrer"
							class="flex-shrink-0 cursor-pointer transition-transform hover:scale-125"
						>
							<svelte:component this={skill.icon} class="h-16 w-16" style="color: {skill.color}" />
						</a>
					{/each}
				</div>

				<!-- Gradient overlays -->
				<div
					class="pointer-events-none absolute top-0 bottom-0 left-0 w-32 bg-gradient-to-r from-background/80 to-transparent"
				></div>
				<div
					class="pointer-events-none absolute top-0 right-0 bottom-0 w-32 bg-gradient-to-l from-background/80 to-transparent"
				></div>
			</div>
		</div>
	</Motion>

	<div class="mx-auto max-w-4xl px-4 sm:px-6 lg:px-8">
		<!-- Values Section -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.3 }}
		>
			<div use:motion class="mt-16">
				<h2 class="font-display mb-8 text-3xl font-bold text-foreground">Mes valeurs</h2>
				<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
					{#each values as value, index}
						<Motion
							let:motion
							initial={{ opacity: 0, y: 20 }}
							animate={{ opacity: 1, y: 0 }}
							transition={{ duration: 0.6, delay: 0.4 + index * 0.1 }}
						>
							<div use:motion>
								<Card class="h-full transition-shadow hover:shadow-lg">
									<CardContent class="p-6">
										<svelte:component this={value.icon} class="mb-4 h-10 w-10 text-secondary" />
										<h3 class="font-display mb-2 text-xl font-semibold text-foreground">
											{value.title}
										</h3>
										<p class="leading-relaxed text-muted-foreground">{value.description}</p>
									</CardContent>
								</Card>
							</div>
						</Motion>
					{/each}
				</div>
			</div>
		</Motion>
	</div>

	<!-- Frameworks Carousel -->
	<Motion
		let:motion
		initial={{ opacity: 0, y: 20 }}
		animate={{ opacity: 1, y: 0 }}
		transition={{ duration: 0.6, delay: 0.5 }}
	>
		<div use:motion class="mt-16">
			<div
				class="relative -mx-4 overflow-hidden border-y border-border bg-card/30 py-8 backdrop-blur-md sm:-mx-6 lg:-mx-8"
			>
				<div class="animate-scroll flex flex-row flex-nowrap gap-12 px-8">
					{#each [...frameworks, ...frameworks, ...frameworks, ...frameworks] as skill}
						<a
							href={skill.url}
							target="_blank"
							rel="noopener noreferrer"
							class="flex-shrink-0 cursor-pointer transition-transform hover:scale-125"
						>
							<svelte:component this={skill.icon} class="h-16 w-16" style="color: {skill.color}" />
						</a>
					{/each}
				</div>

				<!-- Gradient overlays -->
				<div
					class="pointer-events-none absolute top-0 bottom-0 left-0 w-32 bg-gradient-to-r from-background/80 to-transparent"
				></div>
				<div
					class="pointer-events-none absolute top-0 right-0 bottom-0 w-32 bg-gradient-to-l from-background/80 to-transparent"
				></div>
			</div>
		</div>
	</Motion>

	<div class="mx-auto max-w-4xl px-4 sm:px-6 lg:px-8">
		<!-- Parcours Section -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.6 }}
		>
			<div use:motion class="mt-16">
				<h2 class="font-display mb-6 text-3xl font-bold text-foreground">Mon parcours</h2>
				<div class="prose prose-lg max-w-none">
					<p class="mb-6 text-lg leading-relaxed text-muted-foreground">
						Passionné par la technologie depuis mon plus jeune âge, j'ai commencé à coder en
						autodidacte avant de me former de manière plus structurée. Chaque projet est pour moi
						une opportunité d'apprendre et de perfectionner mes compétences.
					</p>
				</div>
			</div>
		</Motion>
	</div>

	<!-- Tools Carousel -->
	<Motion
		let:motion
		initial={{ opacity: 0, y: 20 }}
		animate={{ opacity: 1, y: 0 }}
		transition={{ duration: 0.6, delay: 0.7 }}
	>
		<div use:motion class="mt-16">
			<div
				class="relative -mx-4 overflow-hidden border-y border-border bg-card/30 py-8 backdrop-blur-md sm:-mx-6 lg:-mx-8"
			>
				<div class="animate-scroll flex flex-row flex-nowrap gap-12 px-8">
					{#each [...tools, ...tools, ...tools, ...tools] as skill}
						<a
							href={skill.url}
							target="_blank"
							rel="noopener noreferrer"
							class="flex-shrink-0 cursor-pointer transition-transform hover:scale-125"
						>
							<svelte:component this={skill.icon} class="h-16 w-16" style="color: {skill.color}" />
						</a>
					{/each}
				</div>

				<!-- Gradient overlays -->
				<div
					class="pointer-events-none absolute top-0 bottom-0 left-0 w-32 bg-gradient-to-r from-background/80 to-transparent"
				></div>
				<div
					class="pointer-events-none absolute top-0 right-0 bottom-0 w-32 bg-gradient-to-l from-background/80 to-transparent"
				></div>
			</div>
		</div>
	</Motion>
</main>

<style>
	@keyframes scroll {
		0% {
			transform: translateX(0%);
		}
		100% {
			transform: translateX(-50%);
		}
	}

	.animate-scroll {
		animation: scroll 60s linear infinite alternate;
	}

	.animate-scroll:hover {
		animation-play-state: paused;
	}
</style>
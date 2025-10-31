<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent } from '$lib/components/ui/card/index.js';
	import { Code2, Palette, Rocket, Users } from '@lucide/svelte';
	import { browser } from '$app/environment';
	import { onMount } from 'svelte';

	// Langages
	import IconVuejs from '~icons/devicon/vuejs';
	import IconReact from '~icons/devicon/react';
	import IconAngular from '~icons/devicon/angular';
	import IconSvelte from '~icons/devicon/svelte';
	import IconJavascript from '~icons/devicon/javascript';
	import IconTypescript from '~icons/devicon/typescript';
	import IconNodejs from '~icons/devicon/nodejs';
	import IconPython from '~icons/devicon/python';
	import IconC from '~icons/devicon/c';
	import IconCplusplus from '~icons/devicon/cplusplus';
	import IconSql from '~icons/devicon/mysql';
	import IconHtml5 from '~icons/devicon/html5';
	import IconCss3 from '~icons/devicon/css3';
	import IconBash from '~icons/devicon/bash';
	import IconBashWhite from '~icons/simple-icons/gnubash';

	// Frameworks & Outils
	import IconJava from '~icons/devicon/java';
	import IconSymfony from '~icons/devicon/symfony';
	import IconSymfonyWhite from '~icons/simple-icons/symfony';
	import IconPhp from '~icons/devicon/php';
	import IconMongodb from '~icons/devicon/mongodb';
	import IconNeo4j from '~icons/simple-icons/neo4j';
	import IconElasticsearch from '~icons/simple-icons/elasticsearch';
	import IconAndroid from '~icons/devicon/android';
	import IconTailwindcss from '~icons/devicon/tailwindcss';

	// Outils de développement
	import IconVscode from '~icons/devicon/vscode';
	import IconGit from '~icons/devicon/git';
	import IconFigma from '~icons/devicon/figma';
	import IconSwagger from '~icons/simple-icons/swagger';
	import IconConfluence from '~icons/devicon/confluence';
	import IconJira from '~icons/devicon/jira';
	import IconDocker from '~icons/devicon/docker';
	import IconShadcn from '~icons/simple-icons/shadcnui';
	import IconDaisyui from '~icons/simple-icons/daisyui';

	type Skill = {
		name: string;
		icon: any;
		iconDark?: any;
		color: string;
		colorDark?: string;
		url: string;
	};

	let isDark = $state(false);

	onMount(() => {
		if (browser) {
			isDark = document.documentElement.classList.contains('dark');

			const observer = new MutationObserver(() => {
				isDark = document.documentElement.classList.contains('dark');
			});

			observer.observe(document.documentElement, {
				attributes: true,
				attributeFilter: ['class']
			});

			return () => observer.disconnect();
		}
	});

	function getSkillIcon(skill: Skill) {
		return isDark && skill.iconDark ? skill.iconDark : skill.icon;
	}

	function getSkillColor(skill: Skill) {
		return isDark && skill.colorDark ? skill.colorDark : skill.color;
	}

	const languages: Skill[] = [
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
		{ name: 'Python', icon: IconPython, color: '#3776AB', url: 'https://www.python.org' },
		{ name: 'Java', icon: IconJava, color: '#007396', url: 'https://www.java.com' },
		{ name: 'PHP', icon: IconPhp, color: '#777BB4', url: 'https://www.php.net' },
		{
			name: 'C',
			icon: IconC,
			color: '#A8B9CC',
			url: 'https://en.wikipedia.org/wiki/C_(programming_language)'
		},
		{ name: 'C++', icon: IconCplusplus, color: '#00599C', url: 'https://isocpp.org' },
		{ name: 'SQL', icon: IconSql, color: '#4479A1', url: 'https://www.w3schools.com/sql' },
		{
			name: 'HTML5',
			icon: IconHtml5,
			color: '#E34F26',
			url: 'https://developer.mozilla.org/en-US/docs/Web/HTML'
		},
		{
			name: 'CSS3',
			icon: IconCss3,
			color: '#1572B6',
			url: 'https://developer.mozilla.org/en-US/docs/Web/CSS'
		},
		{
			name: 'Bash',
			icon: IconBash,
			iconDark: IconBashWhite,
			color: '#4EAA25',
			colorDark: '#89E051',
			url: 'https://www.gnu.org/software/bash'
		}
	];

	const frameworks: Skill[] = [
		{ name: 'React', icon: IconReact, color: '#61DAFB', url: 'https://react.dev' },
		{ name: 'Vue.js', icon: IconVuejs, color: '#4FC08D', url: 'https://vuejs.org' },
		{ name: 'Angular', icon: IconAngular, color: '#DD0031', url: 'https://angular.io' },
		{ name: 'Svelte', icon: IconSvelte, color: '#FF3E00', url: 'https://svelte.dev' },
		{ name: 'Node.js', icon: IconNodejs, color: '#339933', url: 'https://nodejs.org' },
		{
			name: 'Symfony',
			icon: IconSymfony,
			iconDark: IconSymfonyWhite,
			color: '#000000',
			colorDark: '#FFFFFF',
			url: 'https://symfony.com'
		},
		{ name: 'Android', icon: IconAndroid, color: '#3DDC84', url: 'https://developer.android.com' },
		{
			name: 'Shadcn/ui',
			icon: IconShadcn,
			iconDark: IconShadcn,
			color: '#000000',
			colorDark: '#FFFFFF',
			url: 'https://ui.shadcn.com'
		},
		{ name: 'DaisyUI', icon: IconDaisyui, color: '#5A0EF8', url: 'https://daisyui.com' },
		{
			name: 'TailwindCSS',
			icon: IconTailwindcss,
			iconDark: IconTailwindcss,
			color: '#06B6D4',
			colorDark: '#06B6D4',
			url: 'https://tailwindcss.com'
		}
	];

	const tools: Skill[] = [
		{ name: 'VS Code', icon: IconVscode, color: '#007ACC', url: 'https://code.visualstudio.com' },
		{ name: 'Git', icon: IconGit, color: '#F05032', url: 'https://git-scm.com' },
		{ name: 'Docker', icon: IconDocker, color: '#2496ED', url: 'https://www.docker.com' },
		{ name: 'MongoDB', icon: IconMongodb, color: '#47A248', url: 'https://www.mongodb.com' },
		{ name: 'Neo4j', icon: IconNeo4j, color: '#4581C3', url: 'https://neo4j.com' },
		{
			name: 'Elasticsearch',
			icon: IconElasticsearch,
			color: '#005571',
			url: 'https://www.elastic.co'
		},
		{ name: 'Figma', icon: IconFigma, color: '#F24E1E', url: 'https://www.figma.com' },
		{ name: 'Swagger', icon: IconSwagger, color: '#85EA2D', url: 'https://swagger.io' },
		{
			name: 'Confluence',
			icon: IconConfluence,
			color: '#172B4D',
			url: 'https://www.atlassian.com/software/confluence'
		},
		{
			name: 'Jira',
			icon: IconJira,
			color: '#0052CC',
			url: 'https://www.atlassian.com/software/jira'
		}
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

<svelte:head>
	<title>À propos - Hugo Föllmi</title>
	<meta
		name="description"
		content="Découvrez mon parcours, mes compétences et mes valeurs en développement web et mobile"
	/>
</svelte:head>

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
					<p
						class="mb-6 text-justify text-lg leading-relaxed text-muted-foreground
"
					>
						Je m'appelle Hugo Föllmi, j'ai 21 ans et je suis né le 11 novembre 2004 à Santiago du
						Chili. Je suis passionné par le développement informatique et la création d'applications
						innovantes.
					</p>
					<p class="mb-6 text-justify text-lg leading-relaxed text-muted-foreground">
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
						{@const SkillIcon = getSkillIcon(skill)}
						<a
							href={skill.url}
							target="_blank"
							rel="noopener noreferrer"
							class="flex-shrink-0 cursor-pointer transition-transform hover:scale-125"
						>
							<SkillIcon class="h-16 w-16" style="color: {getSkillColor(skill)}" />
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
						{@const ValueIcon = value.icon}
						<Motion
							let:motion
							initial={{ opacity: 0, y: 20 }}
							animate={{ opacity: 1, y: 0 }}
							transition={{ duration: 0.6, delay: 0.4 + index * 0.1 }}
						>
							<div use:motion>
								<Card class="h-full transition-shadow hover:shadow-lg">
									<CardContent class="p-6">
										<ValueIcon class="mb-4 h-10 w-10 text-secondary" />
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
						{@const SkillIcon = getSkillIcon(skill)}
						<a
							href={skill.url}
							target="_blank"
							rel="noopener noreferrer"
							class="flex-shrink-0 cursor-pointer transition-transform hover:scale-125"
						>
							<SkillIcon class="h-16 w-16" style="color: {getSkillColor(skill)}" />
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
					<p class="mb-6 text-justify text-lg leading-relaxed text-muted-foreground">
						Passionné par la technologie depuis mon plus jeune âge, j'ai commencé à coder en
						autodidacte avant de me former de manière plus structurée. Après un BAC technologique
						STI2D obtenu en 2022, j'ai eu l'opportunité de poursuivre mes études en BUT Informatique
						à l'IUT de Grenoble. J'ai fait le choix de réaliser ma dernière année de BUT en
						alternance afin de me former dans un environnement professionnel.
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
						{@const SkillIcon = getSkillIcon(skill)}
						<a
							href={skill.url}
							target="_blank"
							rel="noopener noreferrer"
							class="flex-shrink-0 cursor-pointer transition-transform hover:scale-125"
						>
							<SkillIcon class="h-16 w-16" style="color: {getSkillColor(skill)}" />
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

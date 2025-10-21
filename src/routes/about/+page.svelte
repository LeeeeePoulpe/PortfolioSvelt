<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent } from '$lib/components/ui/card/index.js';
	import { Code2, Palette, Rocket, Users } from '@lucide/svelte';

	// Langages
	import IconVuejs from '~icons/devicon/vuejs';
	import IconReact from '~icons/devicon/react';
	import IconAngular from '~icons/devicon/angular';
	import IconSvelte from '~icons/devicon/svelte';
	import IconJavascript from '~icons/devicon/javascript';
	import IconTypescript from '~icons/devicon/typescript';
	import IconNodejs from '~icons/devicon/nodejs';
	import IconPython from '~icons/devicon/python';

	// Frameworks & Outils
	import IconJava from '~icons/devicon/java';
	import IconSymfony from '~icons/devicon/symfony';
	import IconPhp from '~icons/devicon/php';
	import IconMongodb from '~icons/devicon/mongodb';
	import IconNeo4j from '~icons/simple-icons/neo4j';
	import IconElasticsearch from '~icons/simple-icons/elasticsearch';
	import IconAndroid from '~icons/devicon/android';

	// Outils de développement
	import IconVscode from '~icons/devicon/vscode';
	import IconGit from '~icons/devicon/git';
	import IconFigma from '~icons/devicon/figma';
	import IconSwagger from '~icons/simple-icons/swagger';
	import IconConfluence from '~icons/devicon/confluence';
	import IconJira from '~icons/devicon/jira';
	import IconDocker from '~icons/devicon/docker';
	import IconShadcn from '~icons/simple-icons/shadcnui';

	const skills = [
		{
			category: 'Langages & Frameworks Frontend',
			items: [
				{ name: 'Vue.js', icon: IconVuejs, color: '#4FC08D', url: 'https://vuejs.org/' },
				{ name: 'React', icon: IconReact, color: '#61DAFB', url: 'https://react.dev/' },
				{ name: 'Angular', icon: IconAngular, color: '#DD0031', url: 'https://angular.dev/' },
				{ name: 'Svelte', icon: IconSvelte, color: '#FF3E00', url: 'https://svelte.dev/' },
				{ name: 'JavaScript', icon: IconJavascript, color: '#F7DF1E', url: 'https://developer.mozilla.org/en-US/docs/Web/JavaScript' },
				{ name: 'TypeScript', icon: IconTypescript, color: '#3178C6', url: 'https://www.typescriptlang.org/' },
				{ name: 'Node.js', icon: IconNodejs, color: '#339933', url: 'https://nodejs.org/' },
				{ name: 'Python', icon: IconPython, color: '#3776AB', url: 'https://www.python.org/' }
			]
		},
		{
			category: 'Backend & Bases de données',
			items: [
				{ name: 'Android', icon: IconAndroid, color: '#3DDC84', url: 'https://developer.android.com/' },
				{ name: 'Java', icon: IconJava, color: '#007396', url: 'https://docs.oracle.com/en/java/' },
				{ name: 'Symfony', icon: IconSymfony, color: '#000000', url: 'https://symfony.com/doc/current/index.html' },
				{ name: 'PHP', icon: IconPhp, color: '#777BB4', url: 'https://www.php.net/' },
				{ name: 'MongoDB', icon: IconMongodb, color: '#47A248', url: 'https://www.mongodb.com/docs/' },
				{ name: 'Neo4j', icon: IconNeo4j, color: '#008CC1', url: 'https://neo4j.com/docs/' },
				{ name: 'Elasticsearch', icon: IconElasticsearch, color: '#005571', url: 'https://www.elastic.co/guide/index.html' }
			]
		},
		{
			category: 'Outils de développement',
			items: [
				{ name: 'VS Code', icon: IconVscode, color: '#007ACC', url: 'https://code.visualstudio.com/docs' },
				{ name: 'Git', icon: IconGit, color: '#F05032', url: 'https://git-scm.com/doc' },
				{ name: 'Figma', icon: IconFigma, color: '#F24E1E', url: 'https://help.figma.com/' },
				{ name: 'Shadcn UI', icon: IconShadcn, color: '#000000', url: 'https://ui.shadcn.com/' },
				{ name: 'Swagger', icon: IconSwagger, color: '#85EA2D', url: 'https://swagger.io/docs/' },
				{ name: 'Confluence', icon: IconConfluence, color: '#172B4D', url: 'https://support.atlassian.com/confluence-cloud/' },
				{ name: 'Jira', icon: IconJira, color: '#0052CC', url: 'https://support.atlassian.com/jira-software-cloud/' },
				{ name: 'Docker', icon: IconDocker, color: '#2496ED', url: 'https://docs.docker.com/' }
			]
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

<main class="min-h-screen px-4 pt-32 pb-16 sm:px-6 lg:px-8">
	<div class="mx-auto max-w-4xl">
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

		<!-- Values Section -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.2 }}
		>
			<div use:motion class="mt-16">
				<h2 class="font-display mb-8 text-3xl font-bold text-foreground">Mes valeurs</h2>
				<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
					{#each values as value, index}
						<Motion
							let:motion
							initial={{ opacity: 0, y: 20 }}
							animate={{ opacity: 1, y: 0 }}
							transition={{ duration: 0.6, delay: 0.3 + index * 0.1 }}
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

		<!-- Skills Section -->
		<Motion
			let:motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.4 }}
		>
			<div use:motion class="mt-16">
				<h2 class="font-display mb-8 text-3xl font-bold text-foreground">Compétences</h2>
				<div class="space-y-8">
					{#each skills as skillGroup, groupIndex}
						<Motion
							let:motion
							initial={{ opacity: 0, y: 20 }}
							animate={{ opacity: 1, y: 0 }}
							transition={{ duration: 0.6, delay: 0.5 + groupIndex * 0.1 }}
						>
							<div use:motion>
								<h3 class="font-display mb-4 text-xl font-semibold text-foreground">
									{skillGroup.category}
								</h3>
								<div class="grid grid-cols-2 gap-4 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6">
									{#each skillGroup.items as skill, index}
										<Motion
											let:motion
											initial={{ opacity: 0, scale: 0.8 }}
											animate={{ opacity: 1, scale: 1 }}
											transition={{ duration: 0.4, delay: 0.6 + groupIndex * 0.1 + index * 0.05 }}
											whileHover={{ scale: 1.05, y: -5 }}
										>
											<div use:motion>
												<a
													href={skill.url}
													target="_blank"
													rel="noopener noreferrer"
													class="block h-full"
												>
													<Card
														class="group h-full cursor-pointer transition-all hover:border-accent hover:shadow-lg"
													>
														<CardContent class="flex flex-col items-center justify-center gap-3 p-4">
															<svelte:component
																this={skill.icon}
																class="h-10 w-10 transition-colors"
																style="color: {skill.color}"
															/>
															<span
																class="text-center text-sm font-medium text-muted-foreground transition-colors group-hover:text-foreground"
															>
																{skill.name}
															</span>
														</CardContent>
													</Card>
												</a>
											</div>
										</Motion>
									{/each}
								</div>
							</div>
						</Motion>
					{/each}
				</div>
			</div>
		</Motion>
	</div>
</main>

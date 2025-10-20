<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { Card, CardContent } from '$lib/components/ui/card/index.js';
	import { Code2, Palette, Rocket, Users } from '@lucide/svelte';

	const skills = [
		{
			category: 'Langages',
			items: ['Java', 'Python', 'JavaScript', 'TypeScript', 'PHP', 'SQL']
		},
		{
			category: 'Frameworks',
			items: ['Symfony', 'React', 'Next.js', 'Node.js', 'Android']
		},
		{
			category: 'Outils',
			items: ['Git', 'Docker', 'PostgreSQL', 'MongoDB', 'Figma']
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

<main class="min-h-screen px-4 pb-16 pt-32 sm:px-6 lg:px-8">
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
										<svelte:component
											this={value.icon}
											class="mb-4 h-10 w-10 text-secondary"
										/>
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
				<div class="grid grid-cols-1 gap-6 md:grid-cols-3">
					{#each skills as skillGroup, index}
						<Motion
							let:motion
							initial={{ opacity: 0, y: 20 }}
							animate={{ opacity: 1, y: 0 }}
							transition={{ duration: 0.6, delay: 0.5 + index * 0.1 }}
						>
							<div use:motion>
								<Card>
									<CardContent class="p-6">
										<h3 class="font-display mb-4 text-xl font-semibold text-foreground">
											{skillGroup.category}
										</h3>
										<ul class="space-y-2">
											{#each skillGroup.items as skill}
												<li class="flex items-center text-muted-foreground">
													<span class="mr-3 h-2 w-2 rounded-full bg-secondary"></span>
													{skill}
												</li>
											{/each}
										</ul>
									</CardContent>
								</Card>
							</div>
						</Motion>
					{/each}
				</div>
			</div>
		</Motion>
	</div>
</main>


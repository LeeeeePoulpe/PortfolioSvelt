<script lang="ts">
	import { Motion } from 'svelte-motion';
	import {
		Card,
		CardContent,
		CardDescription,
		CardHeader,
		CardTitle
	} from '$lib/components/ui/card/index.js';
	import Button from '$lib/components/ui/button/button.svelte';
	import Input from '$lib/components/ui/input/input.svelte';
	import Textarea from '$lib/components/ui/textarea/textarea.svelte';
	import Label from '$lib/components/ui/label/label.svelte';
	import { Github, Linkedin, Mail, MapPin } from '@lucide/svelte';

	const contactInfo = [
		{
			icon: Mail,
			label: 'Email',
			value: 'hugofollmi@gmail.com',
			href: 'mailto:hugofollmi@gmail.com'
		},
		{
			icon: Github,
			label: 'GitHub',
			value: 'github.com',
			href: 'https://www.github.com/LeeeeePoulpe'
		},
		{
			icon: Linkedin,
			label: 'LinkedIn',
			value: 'linkedin.com',
			href: 'https://www.linkedin.com/in/hugo-follmi-71a971214/'
		},
		{
			icon: MapPin,
			label: 'Localisation',
			value: 'Grenoble, France',
			href: null
		}
	];

	let status = $state('');
	const WEB3FORMS_ACCESS_KEY =
		import.meta.env.PUBLIC_WEB3FORMS_ACCESS_KEY || '0950e898-368a-4c48-869a-ccf5a9801931';

	const handleSubmit = async (e: SubmitEvent) => {
		e.preventDefault();
		status = 'Envoi en cours...';

		const form = e.currentTarget as HTMLFormElement;
		const formData = new FormData(form);
		const object = Object.fromEntries(formData);
		const json = JSON.stringify(object);

		try {
			const response = await fetch('https://api.web3forms.com/submit', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json',
					Accept: 'application/json'
				},
				body: json
			});

			const result = await response.json();
			console.log('Réponse complète:', result);

			if (result.success === true) {
				status = 'Message envoyé avec succès ! Je vous répondrai bientôt.';
				form.reset();
			} else {
				console.error('Erreur Web3Forms:', result);
				status = result.message || 'Une erreur est survenue. Veuillez réessayer.';
			}
		} catch (error) {
			console.error('Erreur lors de la requête:', error);
			status = 'Une erreur est survenue. Veuillez réessayer.';
		}

		setTimeout(() => {
			status = '';
		}, 5000);
	};
</script>

<svelte:head>
	<title>Contact - Hugo Föllmi</title>
	<meta name="description" content="Contactez-moi pour discuter de vos projets ou opportunités professionnelles" />
</svelte:head>

<main class="min-h-screen px-4 pt-32 pb-16 sm:px-6 lg:px-8">
	<div class="mx-auto max-w-5xl">
		<Motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6 }}
			let:motion
		>
			<div use:motion>
				<h1 class="font-display mb-4 text-4xl font-bold text-foreground sm:text-5xl">
					Me contacter
				</h1>
				<p class="mb-8 text-lg leading-relaxed text-muted-foreground">
					Une question, un projet ou simplement envie d'échanger ? N'hésitez pas à me contacter !
				</p>
			</div>
		</Motion>

		<Motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.1 }}
			let:motion
		>
			<div use:motion class="mb-8">
				<Card
					class="relative overflow-hidden border-2 border-green-500/20 bg-gradient-to-br from-green-500/5 via-background to-background shadow-lg shadow-green-500/5"
				>
					<div
						class="absolute top-0 right-0 h-32 w-32 translate-x-8 -translate-y-8 rounded-full bg-green-500/10 blur-3xl"
					></div>
					<CardContent class="relative px-6 py-5">
						<div class="flex items-start gap-4">
							<div
								class="flex h-12 w-12 shrink-0 items-center justify-center rounded-full bg-green-500/10 ring-2 ring-green-500/20"
							>
								<div class="h-3 w-3 animate-pulse rounded-full bg-green-500"></div>
							</div>
							<div class="flex-1">
								<h3 class="font-display mb-2 text-xl font-bold text-foreground">
									Actuellement disponible
								</h3>
								<p class="leading-relaxed text-muted-foreground">
									Je suis à la recherche d'opportunités professionnelles. N'hésitez pas à me
									contacter pour discuter de vos projets !
								</p>
							</div>
						</div>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<div class="grid grid-cols-1 gap-8 lg:grid-cols-2 lg:items-start">
			<Motion
				initial={{ opacity: 0, x: -20 }}
				animate={{ opacity: 1, x: 0 }}
				transition={{ duration: 0.6, delay: 0.2 }}
				let:motion
			>
				<div use:motion class="flex h-full">
					<Card class="flex-1">
						<CardHeader>
							<CardTitle class="font-display">Envoyez-moi un message</CardTitle>
							<CardDescription>Je vous répondrai dans les plus brefs délais</CardDescription>
						</CardHeader>
						<CardContent>
							<form class="space-y-4" onsubmit={handleSubmit}>
								<input type="hidden" name="access_key" value={WEB3FORMS_ACCESS_KEY} />

								<div class="space-y-2">
									<Label for="name">Nom</Label>
									<Input id="name" name="name" placeholder="Votre nom" required />
								</div>
								<div class="space-y-2">
									<Label for="email">Email</Label>
									<Input
										id="email"
										name="email"
										type="email"
										placeholder="votre@email.com"
										required
									/>
								</div>
								<div class="space-y-2">
									<Label for="subject">Sujet</Label>
									<Input
										id="subject"
										name="subject"
										placeholder="Sujet de votre message"
										required
									/>
								</div>
								<div class="space-y-2">
									<Label for="message">Message</Label>
									<Textarea
										id="message"
										name="message"
										placeholder="Votre message..."
										rows={6}
										class="resize-none"
										required
									/>
								</div>

								{#if status}
									<div
										class="rounded-lg p-3 text-sm {status.includes('succès') ||
										status.includes('Success')
											? 'bg-green-500/10 text-green-600 dark:text-green-400'
											: status === 'Envoi en cours...'
												? 'bg-blue-500/10 text-blue-600 dark:text-blue-400'
												: 'bg-red-500/10 text-red-600 dark:text-red-400'}"
									>
										{status}
									</div>
								{/if}

								<Button type="submit" class="w-full" disabled={status === 'Envoi en cours...'}>
									{status === 'Envoi en cours...' ? 'Envoi en cours...' : 'Envoyer le message'}
								</Button>
							</form>
						</CardContent>
					</Card>
				</div>
			</Motion>

			<Motion
				initial={{ opacity: 0, x: 20 }}
				animate={{ opacity: 1, x: 0 }}
				transition={{ duration: 0.6, delay: 0.3 }}
				let:motion
			>
				<div use:motion class="flex h-full">
					<Card class="flex-1">
						<CardHeader>
							<CardTitle class="font-display">Informations de contact</CardTitle>
							<CardDescription>Retrouvez-moi sur ces différentes plateformes</CardDescription>
						</CardHeader>
						<CardContent class="space-y-4">
							{#each contactInfo as info, index}
								{@const Icon = info.icon}
								<Motion
									initial={{ opacity: 0, y: 10 }}
									animate={{ opacity: 1, y: 0 }}
									transition={{ duration: 0.4, delay: 0.4 + index * 0.1 }}
									let:motion
								>
									{#if info.href}
										<a
											use:motion
											href={info.href}
											target="_blank"
											rel="noopener noreferrer"
											class="flex items-start gap-4 rounded-lg p-3 transition-colors hover:cursor-pointer hover:bg-muted/50"
										>
											<div class="rounded-lg bg-secondary/10 p-2">
												<Icon class="h-5 w-5 text-secondary" />
											</div>
											<div class="flex-1">
												<p class="mb-1 text-sm font-medium text-foreground">{info.label}</p>
												<p
													class="text-sm text-muted-foreground transition-colors group-hover:text-secondary"
												>
													{info.value}
												</p>
											</div>
										</a>
									{:else}
										<div use:motion class="flex items-start gap-4 rounded-lg p-3 transition-colors">
											<div class="rounded-lg bg-secondary/10 p-2">
												<Icon class="h-5 w-5 text-secondary" />
											</div>
											<div class="flex-1">
												<p class="mb-1 text-sm font-medium text-foreground">{info.label}</p>
												<p class="text-sm text-muted-foreground">{info.value}</p>
											</div>
										</div>
									{/if}
								</Motion>
							{/each}
						</CardContent>
					</Card>
				</div>
			</Motion>
		</div>
	</div>
</main>

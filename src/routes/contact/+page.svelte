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
			value: 'contact@hugofollmi.com',
			href: 'mailto:contact@hugofollmi.com'
		},
		{
			icon: Github,
			label: 'GitHub',
			value: 'github.com/hugofollmi',
			href: 'https://github.com/hugofollmi'
		},
		{
			icon: Linkedin,
			label: 'LinkedIn',
			value: 'linkedin.com/in/hugofollmi',
			href: 'https://linkedin.com/in/hugofollmi'
		},
		{
			icon: MapPin,
			label: 'Localisation',
			value: 'France',
			href: null
		}
	];

	let name = $state('');
	let email = $state('');
	let subject = $state('');
	let message = $state('');

	function handleSubmit(e: SubmitEvent) {
		e.preventDefault();
		// Logique de soumission du formulaire à implémenter
		console.log({ name, email, subject, message });
	}
</script>

<main class="min-h-screen px-4 pb-16 pt-32 sm:px-6 lg:px-8">
	<div class="mx-auto max-w-5xl">
		<Motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6 }}
			let:motion
		>
			<div use:motion>
				<h1 class="mb-4 font-display text-4xl font-bold text-foreground sm:text-5xl">
					Me contacter
				</h1>
				<p class="mb-8 text-lg leading-relaxed text-muted-foreground">
					Une question, un projet ou simplement envie d'échanger ? N'hésitez pas à me contacter !
				</p>
			</div>
		</Motion>

		<!-- Carte de disponibilité -->
		<Motion
			initial={{ opacity: 0, y: 20 }}
			animate={{ opacity: 1, y: 0 }}
			transition={{ duration: 0.6, delay: 0.1 }}
			let:motion
		>
			<div use:motion class="mb-8">
				<Card class="bg-muted/30">
					<CardContent class="px-6 py-2">
						<h3 class="mb-2 font-display text-lg font-semibold text-foreground">
							Disponibilité
						</h3>
						<p class="leading-relaxed text-muted-foreground">
							Je suis actuellement à la recherche d'opportunités professionnelles. N'hésitez pas à
							me contacter pour discuter de vos besoins !
						</p>
					</CardContent>
				</Card>
			</div>
		</Motion>

		<div class="grid grid-cols-1 gap-8 lg:grid-cols-2 lg:items-start">
			<!-- Formulaire de contact -->
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
								<div class="space-y-2">
									<Label for="name">Nom</Label>
									<Input id="name" placeholder="Votre nom" bind:value={name} />
								</div>
								<div class="space-y-2">
									<Label for="email">Email</Label>
									<Input id="email" type="email" placeholder="votre@email.com" bind:value={email} />
								</div>
								<div class="space-y-2">
									<Label for="subject">Sujet</Label>
									<Input id="subject" placeholder="Sujet de votre message" bind:value={subject} />
								</div>
								<div class="space-y-2">
									<Label for="message">Message</Label>
									<Textarea
										id="message"
										placeholder="Votre message..."
										rows={6}
										class="resize-none"
										bind:value={message}
									/>
								</div>
								<Button type="submit" class="w-full">Envoyer le message</Button>
							</form>
						</CardContent>
					</Card>
				</div>
			</Motion>

			<!-- Informations de contact -->
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
									<div
										use:motion
										class="flex items-start gap-4 rounded-lg p-3 transition-colors hover:bg-muted/50"
									>
										<div class="rounded-lg bg-secondary/10 p-2">
											<Icon class="h-5 w-5 text-secondary" />
										</div>
										<div class="flex-1">
											<p class="mb-1 text-sm font-medium text-foreground">{info.label}</p>
											{#if info.href}
												<a
													href={info.href}
													target="_blank"
													rel="noopener noreferrer"
													class="text-sm text-muted-foreground transition-colors hover:text-secondary"
												>
													{info.value}
												</a>
											{:else}
												<p class="text-sm text-muted-foreground">{info.value}</p>
											{/if}
										</div>
									</div>
								</Motion>
							{/each}
						</CardContent>
					</Card>
				</div>
			</Motion>
		</div>
	</div>
</main>


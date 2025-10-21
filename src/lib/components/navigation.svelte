<script lang="ts">
	import { page } from '$app/stores';
	import { cn } from '$lib/utils.js';
	import { Menu, X } from '@lucide/svelte';
	import { Motion } from 'svelte-motion';
	import { slide } from 'svelte/transition';
	import ThemeToggle from './theme-toggle.svelte';
	import Button from './ui/button/button.svelte';

	const navItems = [
		{ href: '/', label: 'Accueil' },
		{ href: '/about', label: 'À propos' },
		{ href: '/projects', label: 'Projets' },
		{ href: '/contact', label: 'Contact' }
	];

	let mobileMenuOpen = $state(false);

	// Équivalent de usePathname() en Svelte
	$effect(() => {
		mobileMenuOpen = false;
	});
</script>

<nav
	class="fixed top-4 right-4 left-4 z-50 rounded-2xl border border-border bg-background/70 shadow-lg backdrop-blur-xl md:left-1/2 md:w-4/5 md:-translate-x-1/2"
>
	<div class="mx-auto max-w-7xl px-6 sm:px-8 lg:px-10">
		<div class="flex h-16 items-center justify-between">
			<a
				href="/"
				class="font-display text-xl font-bold text-foreground transition-colors hover:text-secondary"
			>
				HF
			</a>

			<!-- Desktop Navigation -->
			<div class="hidden items-center gap-8 md:flex">
				{#each navItems as item}
					<a
						href={item.href}
						class={cn(
							'relative text-sm font-medium transition-colors hover:text-secondary',
							$page.url.pathname === item.href ? 'text-secondary' : 'text-muted-foreground'
						)}
					>
						{item.label}
						{#if $page.url.pathname === item.href}
							<span class="absolute right-0 -bottom-[21px] left-0 h-0.5 bg-secondary"></span>
						{/if}
					</a>
				{/each}
				<ThemeToggle />
			</div>

			<!-- Mobile Menu Button -->
			<div class="flex items-center gap-2 hover:cursor-pointer md:hidden">
				<ThemeToggle />
				<Button
					variant="ghost"
					size="icon"
					onclick={() => (mobileMenuOpen = !mobileMenuOpen)}
					aria-label="Toggle menu"
				>
					<div
						class="transition-transform duration-300"
						style="transform: rotate({mobileMenuOpen ? 90 : 0}deg);"
					>
						{#if mobileMenuOpen}
							<X size={24} />
						{:else}
							<Menu size={24} />
						{/if}
					</div>
				</Button>
			</div>
		</div>

		<!-- Mobile Navigation -->
		{#if mobileMenuOpen}
			<div
				class="overflow-hidden border-t border-border md:hidden"
				transition:slide={{ duration: 300 }}
			>
				<div class="py-4">
					{#each navItems as item, i}
						<Motion
							let:motion
							initial={{ opacity: 0, x: -20 }}
							animate={{ opacity: 1, x: 0 }}
							transition={{ duration: 0.3, delay: i * 0.1 }}
						>
							<a
								use:motion
								href={item.href}
								onclick={() => (mobileMenuOpen = false)}
								class={cn(
									'block py-2 text-base font-medium transition-colors',
									$page.url.pathname === item.href
										? 'text-secondary'
										: 'text-muted-foreground hover:text-secondary'
								)}
							>
								{item.label}
							</a>
						</Motion>
					{/each}
				</div>
			</div>
		{/if}
	</div>
</nav>

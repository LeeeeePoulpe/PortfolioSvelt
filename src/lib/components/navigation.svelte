<script lang="ts">
	import { page } from '$app/stores';
	import { cn } from '$lib/utils.js';
	import { Menu, X } from '@lucide/svelte';
	import ThemeToggle from './theme-toggle.svelte';

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

<nav class="fixed top-0 left-0 right-0 z-50 bg-background/80 backdrop-blur-md border-b border-border">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="flex items-center justify-between h-16">
			<a
				href="/"
				class="font-display text-xl font-bold text-foreground hover:text-secondary transition-colors"
			>
				HF
			</a>

			<!-- Desktop Navigation -->
			<div class="hidden md:flex items-center gap-8">
				{#each navItems as item}
					<a
						href={item.href}
						class={cn(
							'text-sm font-medium transition-colors hover:text-primary-navbar relative',
							$page.url.pathname === item.href ? 'text-primary-navbar' : 'text-foreground'
						)}
					>
						{item.label}
						{#if $page.url.pathname === item.href}
							<span class="absolute -bottom-[21px] left-0 right-0 h-0.5 bg-primary-navbar"></span>
						{/if}
					</a>
				{/each}
				<ThemeToggle />
			</div>

			<!-- Mobile Menu Button -->
			<div class="md:hidden flex items-center gap-2">
				<ThemeToggle />
				<button
					class="p-2 text-foreground"
					onclick={() => (mobileMenuOpen = !mobileMenuOpen)}
					aria-label="Toggle menu"
				>
					{#if mobileMenuOpen}
						<X size={24} />
					{:else}
						<Menu size={24} />
					{/if}
				</button>
			</div>
		</div>

		<!-- Mobile Navigation -->
		{#if mobileMenuOpen}
			<div class="md:hidden py-4 border-t border-border">
				{#each navItems as item}
					<a
						href={item.href}
						onclick={() => (mobileMenuOpen = false)}
						class={cn(
							'block py-2 text-base font-medium transition-colors',
							$page.url.pathname === item.href
								? 'text-primary-navbar'
								: 'text-muted-foreground hover:text-primary-navbar'
						)}
					>
						{item.label}
					</a>
				{/each}
			</div>
		{/if}
	</div>
</nav>


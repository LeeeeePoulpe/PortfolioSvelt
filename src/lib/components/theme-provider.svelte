<script module lang="ts">
	import { writable } from 'svelte/store';

	type Theme = 'dark' | 'light' | 'system';

	interface ThemeStore {
		theme: Theme;
		setTheme: (theme: Theme) => void;
	}

	// Store global pour le thème
	const themeStore = writable<ThemeStore>({
		theme: 'system',
		setTheme: () => {}
	});

	// Export pour utilisation dans d'autres composants (équivalent de useTheme)
	export function useTheme() {
		return themeStore;
	}
</script>

<script lang="ts">
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';

	interface Props {
		defaultTheme?: Theme;
		storageKey?: string;
		children?: import('svelte').Snippet;
	}

	let { defaultTheme = 'system', storageKey = 'portfolio-theme', children }: Props = $props();

	let theme = $state<Theme>(defaultTheme);
	let mounted = $state(false);

	function applyTheme(newTheme: Theme) {
		if (!browser) return;

		const root = document.documentElement;
		root.classList.remove('light', 'dark');

		if (newTheme === 'system') {
			const systemTheme = window.matchMedia('(prefers-color-scheme: dark)').matches
				? 'dark'
				: 'light';
			root.classList.add(systemTheme);
		} else {
			root.classList.add(newTheme);
		}
	}

	function setTheme(newTheme: Theme) {
		theme = newTheme;
		if (browser) {
			localStorage.setItem(storageKey, newTheme);
			applyTheme(newTheme);

			// Mettre à jour le store global
			themeStore.set({
				theme: newTheme,
				setTheme
			});
		}
	}

	onMount(() => {
		// Charger le thème depuis le localStorage
		const stored = localStorage.getItem(storageKey) as Theme | null;
		if (stored) {
			theme = stored;
		}

		applyTheme(theme);

		// Écouter les changements de préférence système
		const mediaQuery = window.matchMedia('(prefers-color-scheme: dark)');
		const handleChange = () => {
			if (theme === 'system') {
				applyTheme('system');
			}
		};

		mediaQuery.addEventListener('change', handleChange);

		// Initialiser le store global
		themeStore.set({
			theme,
			setTheme
		});

		mounted = true;

		return () => {
			mediaQuery.removeEventListener('change', handleChange);
		};
	});
</script>

{#if mounted}
	{@render children?.()}
{:else}
	<!-- Éviter le flash pendant le chargement -->
	<div style="visibility: hidden;">
		{@render children?.()}
	</div>
{/if}

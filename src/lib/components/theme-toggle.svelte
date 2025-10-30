<script lang="ts">
	import { Moon, Sun } from '@lucide/svelte';
	import { useTheme } from './theme-provider.svelte';
	import Button from '../components/ui/button/button.svelte';

	const themeStore = useTheme();
	let currentTheme = $state($themeStore.theme);

	// Réagir aux changements du store
	$effect(() => {
		currentTheme = $themeStore.theme;
	});

	function toggleTheme() {
		const newTheme = currentTheme === 'light' ? 'dark' : 'light';
		$themeStore.setTheme(newTheme);
	}
</script>

<Button
	variant="ghost"
	size="icon"
	onclick={toggleTheme}
	class="relative h-9 w-9 rounded-full"
	aria-label="Toggle theme"
>
	<Sun
		class="h-[1.2rem] w-[1.2rem] scale-100 rotate-0 transition-all dark:scale-0 dark:-rotate-90"
	/>
	<Moon
		class="absolute h-[1.2rem] w-[1.2rem] scale-0 rotate-90 transition-all dark:scale-100 dark:rotate-0"
	/>
</Button>

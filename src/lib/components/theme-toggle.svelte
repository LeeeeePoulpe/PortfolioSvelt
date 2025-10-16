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
	class="relative w-9 h-9 rounded-full"
	aria-label="Toggle theme"
>
	<Sun class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
	<Moon class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
</Button>


<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { onMount, onDestroy } from 'svelte';
	import { writable } from 'svelte/store';

	const activeSection = writable(0);
	let scrollHandler: (() => void) | null = null;

	onMount(() => {
		scrollHandler = () => {
			const scrollPosition = window.scrollY;
			const windowHeight = window.innerHeight;

			if (scrollPosition < windowHeight - 64) {
				activeSection.set(0);
			} else if (scrollPosition < windowHeight * 2 - 64) {
				activeSection.set(1);
			} else {
				activeSection.set(2);
			}
		};

		window.addEventListener('scroll', scrollHandler);
	});

	onDestroy(() => {
		if (scrollHandler) {
			window.removeEventListener('scroll', scrollHandler);
		}
	});

	function scrollToSection(index: number) {
		const targetScroll = index * (window.innerHeight - 64);
		window.scrollTo({ top: targetScroll, behavior: 'smooth' });
	}
</script>

<Motion
	let:motion
	initial={{ opacity: 0 }}
	animate={{ opacity: 1 }}
	transition={{ duration: 0.6, delay: 1 }}
>
	<div use:motion class="fixed top-1/2 right-6 z-50 hidden -translate-y-1/2 flex-col gap-3 md:flex">
		{#each [0, 1, 2] as index}
			<Motion let:motion>
				<button
					use:motion
					class="h-2 w-2 cursor-pointer rounded-full transition-all {$activeSection === index
						? 'bg-purple-300'
						: 'bg-muted-foreground/20'}"
					on:click={() => scrollToSection(index)}
					aria-label="Aller à la section {index + 1}"
				></button>
			</Motion>
		{/each}
	</div>
</Motion>

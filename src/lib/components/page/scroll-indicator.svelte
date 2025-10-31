<script lang="ts">
	import { Motion } from 'svelte-motion';
	import { onMount, onDestroy } from 'svelte';
	import { writable } from 'svelte/store';

	const activeSection = writable(0);
	let scrollHandler: (() => void) | null = null;

	onMount(() => {
		scrollHandler = () => {
			const sections = document.querySelectorAll('main > section');
			const scrollPosition = window.scrollY + window.innerHeight / 3;
			const documentHeight = document.documentElement.scrollHeight;
			const windowHeight = window.innerHeight;

			// Si on est proche du bas de la page, forcer la dernière section
			if (window.scrollY + windowHeight >= documentHeight - 100) {
				activeSection.set(sections.length - 1);
				return;
			}

			let currentSection = 0;
			sections.forEach((section, index) => {
				const rect = section.getBoundingClientRect();
				const sectionTop = rect.top + window.scrollY;
				const sectionBottom = sectionTop + rect.height;

				if (scrollPosition >= sectionTop && scrollPosition < sectionBottom) {
					currentSection = index;
				}
			});

			activeSection.set(currentSection);
		};

		window.addEventListener('scroll', scrollHandler);
		// Appel initial pour définir la section active au chargement
		scrollHandler();
	});

	onDestroy(() => {
		if (scrollHandler) {
			window.removeEventListener('scroll', scrollHandler);
		}
	});

	function scrollToSection(index: number) {
		const sections = document.querySelectorAll('main > section');
		if (sections[index]) {
			const section = sections[index] as HTMLElement;
			const offset = 64;
			const targetScroll = section.offsetTop - offset;
			window.scrollTo({ top: targetScroll, behavior: 'smooth' });
		}
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

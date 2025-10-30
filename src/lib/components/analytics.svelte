<script lang="ts">
	import { onMount } from 'svelte';
	import { browser } from '$app/environment';
	import { dev } from '$app/environment';

	onMount(() => {
		// N'activer Analytics qu'en production (pas en développement)
		if (browser && !dev) {
			// Import dynamique pour éviter les erreurs avec les bloqueurs de pub
			import('@vercel/analytics')
				.then(({ inject }) => {
					inject();
				})
				.catch(() => {
					// Ignorer silencieusement si bloqué
					console.log('Analytics bloqué - normal en développement');
				});
		}
	});
</script>

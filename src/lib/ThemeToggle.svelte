<script>
	import { onMount } from 'svelte';

	let theme = 'light';

	onMount(() => {
		// Check for saved theme preference or default to light
		const savedTheme = localStorage.getItem('theme') || 'light';
		theme = savedTheme;
		document.documentElement.setAttribute('data-theme', theme);
	});

	function toggleTheme() {
		theme = theme === 'light' ? 'dark' : 'light';
		document.documentElement.setAttribute('data-theme', theme);
		localStorage.setItem('theme', theme);
	}
</script>

<button class="theme-toggle" on:click={toggleTheme}>
	{theme === 'light' ? '🌙 Dark' : '☀️ Light'}
</button>


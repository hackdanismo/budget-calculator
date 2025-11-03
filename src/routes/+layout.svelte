<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<header>
	Page header
</header>

<main role="main">
	{@render children()}
</main>

<footer>
	Page Footer
</footer>
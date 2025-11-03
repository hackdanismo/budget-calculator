<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	import Heading from "$lib/components/Header.svelte";
	import Modal from "$lib/components/Modal.svelte";
	import Button from "$lib/components/Button.svelte";

	let { children } = $props();
	let isModalOpen = $state(false);
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Budget Calculator</title>
</svelte:head>

<Heading on:openModal={() => (isModalOpen = true)} />

<!-- 🔍 Debug: see if this flips to "yes" when clicking the header button -->
<!--<p style="position: fixed; bottom: 1rem; left: 1rem; background: #fff; padding: 0.25rem 0.5rem; border: 1px solid #ccc; z-index: 99999;">
	Modal open (layout): {isModalOpen ? "yes" : "no"}
</p>-->

<Modal
    open={isModalOpen}
    on:close={() => (isModalOpen = false)}
>
    <div>
        <Button
            variant="secondary"
            on:click={() => (isModalOpen = false)}
        >
            Cancel
        </Button>
    </div>
</Modal>

<main role="main">
	{@render children()}
</main>

<footer>
	<div class="container">
		Page Footer
	</div>
</footer>
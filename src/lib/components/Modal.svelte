<script lang="ts">
    import { createEventDispatcher } from "svelte";

    // Controls visibility from the parent
    export let open: boolean = false;
    // Optional: click outside the modal to close
    export let closeOnOverlayClick: boolean = true;

    const dispatch = createEventDispatcher();

    function handleOverlayClick(event: MouseEvent) {
        if (event.target === event.currentTarget && closeOnOverlayClick) {
            dispatch("close");
        }
    }

    function handleKeydown(event: KeyboardEvent) {
        if (event.key === "Escape") {
            dispatch("close");
        }
    }
</script>

{#if open}
    <svelte:window on:keydown={handleKeydown} />

    <div
        class="fixed inset-0 z-40 flex items-center justify-center bg-black/50"
        on:click={handleOverlayClick}
    >
        <div class="bg-white rounded-lg shadow-lg max-w-lg w-full mx-4 p-6">
            <slot />
        </div>
    </div>
{/if}
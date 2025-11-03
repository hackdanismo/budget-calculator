<script lang="ts">
    import Button from "$lib/components/Button.svelte";
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    function openModal() {
        dispatch("openModal");
    }
</script>

<header role="banner">
    <div class="container">
        <nav aria-label="Main navigation">
            <ul>
                <li>
                    <Button
                        variant="primary"
                        on:click={openModal}
                    >
                        Open modal
                    </Button>
                </li>
            </ul>
        </nav>
    </div>
</header>
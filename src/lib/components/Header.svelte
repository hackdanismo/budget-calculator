<script lang="ts">
    import Button from "$lib/components/Button.svelte";
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    function openModal() {
        dispatch("openModal");
    }
</script>

<header class="header" role="banner">
    <div class="container">
        <div class="header__content">
            <div></div>
            <nav aria-label="Main navigation">
                <ul>
                    <li>
                        <Button
                            variant="primary"
                            on:click={openModal}
                        >
                            Add
                        </Button>
                    </li>
                </ul>
            </nav>
        </div>
    </div>
</header>
<script lang="ts">
    import Button from "$lib/components/Button.svelte";

    function save() {
        alert("Saved");
    }
</script>

<div class="container"> 
    <h1>Budget Calculator</h1>
</div>

<!--<Button
    variant="primary"
    on:click={() => (isModalOpen = true)}
>
    Open modal
</Button>-->

<!--<Button on:click={save}>Save</Button>-->
<!--<Button variant="secondary" on:click={() => alert("Cancelled")}>Cancel</Button>-->

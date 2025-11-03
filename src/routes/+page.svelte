<script lang="ts">
    import Button from "$lib/components/Button.svelte";

    function save() {
        alert("Saved");
    }
</script>

<h1>Budget Calculator</h1>

<Button on:click={save}>Save</Button>
<Button variant="secondary" on:click={() => alert("Cancelled")}>Cancel</Button>

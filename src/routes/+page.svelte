<script lang="ts">
    import Button from "$lib/components/Button.svelte";
    import Modal from "$lib/components/Modal.svelte";

    let isModalOpen = false;

    function save() {
        alert("Saved");
    }
</script>

<h1>Budget Calculator</h1>

<Button
    variant="primary"
    on:click={() => (isModalOpen = true)}
>
    Open modal
</Button>

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

<!--<Button on:click={save}>Save</Button>-->
<!--<Button variant="secondary" on:click={() => alert("Cancelled")}>Cancel</Button>-->

<script lang="ts">
    export let type: "button" | "submit" | "reset" = "button";
    export let variant: "primary" | "secondary" | "danger" = "primary";
    export let disabled: boolean = false;
    export let className: string = "";

    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    function handleClick(event: MouseEvent) {
        if (!disabled) {
            dispatch("click", event);
        }
    }
</script>

<button
    {type}
    on:click={handleClick}
    disabled={disabled}
    class={`px-4 py-2 rounded-lg font-semibold transition-colors duration-150 cursor-pointer
        ${variant === 'primary' && 'bg-blue-600 text-white hover:bg-blue-700'}
        ${variant === 'secondary' && 'bg-gray-200 text-gray-800 hover:bg-gray-300'}
        ${variant === 'danger' && 'bg-red-500 text-white hover:bg-red-600'}
        ${disabled && 'opacity-50 cursor-not-allowed'}
        ${className}`
    }
>
    <slot />
</button>
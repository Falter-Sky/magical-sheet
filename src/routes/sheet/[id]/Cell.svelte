<script lang="ts">
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    export let row: number;
    export let column: number;
    export let active: boolean;
    export let value: string;
</script>

<div 
style:--row={row} style:--column={column}
class:active on:click={() => dispatch('select')} >{value}</div>

<style>
    div {
        border: 1px solid gray;
        grid-row: calc(var(--row) + 2);
        grid-column: calc(var(--column) + 2);
    }

    .active {
        border-color: #0078f2;
    }
</style>
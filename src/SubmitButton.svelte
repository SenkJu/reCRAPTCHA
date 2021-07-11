<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    function handleClick() {
        dispatch("submit")
    }
</script>

<button on:click={handleClick} class="button">Verify</button>

<style>
    .button {
        background-color: #4A90E2;
        padding: 10px 20px;
        font-family: sans-serif;
        color: white;
        font-size: 15px;
        font-weight: bold;
        border: none;
        cursor: pointer;
        text-transform: uppercase;
        border-radius: wpx;
    }
</style>
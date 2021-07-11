<script>
    import { fade } from "svelte/transition";

    import Header from "./Header.svelte";
    import Image from "./Image.svelte";
    import SubmitButton from "./SubmitButton.svelte";

    export let failed;
</script>

<div class="captcha" transition:fade>
    <Header />

    <div class="images">
        <Image image="1" />
        <Image image="2" />
        <Image image="3" />
        <Image image="4" />
        <Image image="5" />
        <Image image="6" />
        <Image image="7" />
        <Image image="8" />
        <Image image="9" />
    </div>

    {#if failed}
        <div class="failed">Please select all matching images</div>
    {/if}

    <div class="footer">
        <SubmitButton on:submit />
    </div>
</div>

<style>
    .captcha {
        position: absolute;
        top: 50%;
        left: 53px;
        transform: translateY(-50%);
        box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.75);
        border-radius: 5px;
        padding: 7px;
        background-color: white;
    }

    .failed {
        color: #D65E4E;
        font-weight: bold;
        text-align: center;
        font-size: 12px;
        padding-bottom: 10px;
    }

    .images {
        display: grid;
        grid-template-columns: repeat(3, max-content);
        gap: 5px;
        padding-bottom: 5px;
    }

    .footer {
        border-top: solid 1px #D3D3D3;
        text-align: right;
        padding-top: 10px;
    }
</style>

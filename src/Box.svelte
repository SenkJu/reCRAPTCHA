<script>
    import Captcha from "./Captcha.svelte";

    let captchaShown = false;
    let failed = false;
    let gigaFailed = false;

    function handleClick() {
        captchaShown = !captchaShown;
    }

    function onSubmit(e) {
        if (!failed) {
            failed = true;
        } else {
            captchaShown = false;
            gigaFailed = true;
        }
    }
</script>

<div class="box" on:click|self={handleClick} class:failed={gigaFailed}>
    <button class="button" on:click|self={handleClick}></button>

    {#if captchaShown}
        <Captcha on:submit={onSubmit} {failed} />
    {/if}

    <div class="not-robot">
        {#if gigaFailed}
            Please try again later
        {:else}
            I'm not a robot
        {/if}
    </div>
</div>

<style>
    .box {
        height: 80px;
        width: 300px;
        border: solid 1px #D3D3D3;
        border-radius: 3px;  
        background-color: #F9F9F9;
        display: flex;
        align-items: center;
        padding: 0 12px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    .button {
        height: 30px;
        width: 30px;
        border: solid 2px #C1C1C1;
        margin-right: 10px;
        background-color: white;
    }

    .box.failed .button {
        border-color: #D65E4E;
    }

    .box.failed .not-robot {
        color: #D65E4E;
    }

    .box.failed {
        border-color: #D65E4E;     
    }
</style>
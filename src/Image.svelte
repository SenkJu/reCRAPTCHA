<script>
    export let image;

    let checked = false;

    function handleClick() {
        checked = !checked;
    }
</script>

<div on:click={handleClick} class="wrapper" class:checked>
    <img src="img/images/{image}.jpeg" alt="{image}" class="image">
</div>

<style>
    .image {
        height: 113px;
        width: 113px;
        border-radius: 1px;
        position: relative;
        overflow: hidden;
    }

    .wrapper {
        transition: linear transform .1s;
        position: relative;
    }

    .wrapper.checked {
        transform: scale(.85);
    }

    .wrapper::after {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        background-color: #4480F7;
        color: white;
        border-radius: 50%;
        opacity: 0;
        height: 25px;
        width: 25px;
        background-image: url("../img/checkmark.svg");
        background-size: contain;
        background-position: center;
        background-repeat: no-repeat;
        background-size: 15px;
        transform: translate(-10px, -10px);
        transition: linear opacity .1s;
    }

    .wrapper.checked::after {
        opacity: 1;
    }
</style>

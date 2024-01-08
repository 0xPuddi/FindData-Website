<script>
    import { onMount } from 'svelte';
    let mounted = false;

    export let id;
    export let src;
    export let alt = '';

    let backgroundDataImage;

    // Random images positioning
    function mouseOnEnterEvent(e) {
        if (!mounted) {
            return;
        }

        let randomPositionX =
            Math.random() * (e.fromElement.offsetWidth - e.target.offsetWidth);
        let randomPositionY =
            Math.random() *
            (e.fromElement.offsetHeight - e.target.offsetHeight);

        console.log(randomPositionX);
        console.log(randomPositionY);

        e.target.style.left = randomPositionX + 'px';
        e.target.style.top = randomPositionY + 'px';
    }

    onMount(() => {
        mounted = true;
    });
</script>

<div
    class="background-data-image-container-home"
    {id}
    bind:this={backgroundDataImage}
    on:mouseenter={mouseOnEnterEvent}
>
    <img class="background-data-image-home" {src} {alt} />
</div>

<style>
    .background-data-image-container-home {
        background-color: #192767;
        border-radius: 50%;

        width: 100px;
        height: 100px;

        display: flex;
        align-items: center;
        justify-content: center;

        margin: 0;

        border: 1px solid black;
    }
    .background-data-image-home {
        width: 72px;
        height: 72px;

        display: flex;
        align-items: center;
        justify-content: center;
    }

    #image-0 {
        position: absolute;

        top: 20%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    #image-1 {
        position: absolute;

        top: 30%;
        left: 70%;
        transform: translate(-50%, -50%);
    }
    #image-2 {
        position: absolute;

        top: 50%;
        left: 80%;
        transform: translate(-50%, -50%);
    }
    #image-3 {
        position: absolute;

        top: 70%;
        left: 70%;
        transform: translate(-50%, -50%);
    }
    #image-4 {
        position: absolute;

        top: 80%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    #image-5 {
        position: absolute;

        top: 70%;
        left: 30%;
        transform: translate(-50%, -50%);
    }
    #image-6 {
        position: absolute;

        top: 50%;
        left: 20%;
        transform: translate(-50%, -50%);
    }
    #image-7 {
        position: absolute;

        top: 30%;
        left: 30%;
        transform: translate(-50%, -50%);
    }
</style>

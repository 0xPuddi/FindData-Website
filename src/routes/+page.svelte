<script>
    import BackgroundDataImage from '$lib/BackgroundDataImage.svelte';

    let mouseOnMain;
    function mouseOnMainEvent(e) {
        mouseOnMain = e;
    }

    function redirectToMail() {
        window.location.href =
            'mailto:find.data@outlook.com?subject=Data Inquiry - Service Requested&body=Your message request';
    }
</script>

<main class="home">
    <div class="front-container-home" on:mousemove={mouseOnMainEvent}>
        <h1 class="title-home">Find<span class="color-text">Data</span></h1>
        <p class="text-home">
            All the <b><span class="color-text">data</span></b> you really need.
            At your fingerprint. Now.
        </p>
        <p class="text-proposition-home">
            We offer all sort of services to help you collecting, aggregate,
            manage, and examine your data.<br />We are waiting you!
        </p>
        <button class="button-home" on:click={redirectToMail}>
            <p class="button-text-home">Find it</p>
            <img class="button-image-home" src="/logo_black.svg" alt="" />
        </button>
        <div class="background-container-home">
            <div class="background-container-relative-home">
                <BackgroundDataImage
                    id="image-0"
                    src="/home_white.svg"
                    {mouseOnMain}
                />
                <BackgroundDataImage
                    id="image-1"
                    src="/code_white.svg"
                    {mouseOnMain}
                />
                <BackgroundDataImage
                    id="image-2"
                    src="/person_white.svg"
                    {mouseOnMain}
                />
                <BackgroundDataImage
                    id="image-3"
                    src="/likeDislike_white.svg"
                    {mouseOnMain}
                />
                <BackgroundDataImage
                    id="image-4"
                    src="/shield_white.svg"
                    {mouseOnMain}
                />
                <BackgroundDataImage
                    id="image-5"
                    src="/cube_white.svg"
                    {mouseOnMain}
                />
                <BackgroundDataImage
                    id="image-6"
                    src="/card_white.svg"
                    {mouseOnMain}
                />
                <BackgroundDataImage
                    id="image-7"
                    src="/game_white.svg"
                    {mouseOnMain}
                />
            </div>
        </div>
    </div>
</main>

<style>
    .home {
        position: relative;
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;

        background-color: #fbfbfe;
    }
    .front-container-home {
        height: 100%;
        width: 100%;

        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 2rem;
    }
    .background-container-home {
        position: absolute;

        z-index: 0;

        height: 100%;
        width: 100%;

        opacity: 0.8;

        margin: 0;
    }
    .background-container-relative-home {
        position: relative;
        height: 100%;
        width: 100%;
    }

    .title-home {
        z-index: 2;
        font-size: 5rem;
    }

    .text-home {
        z-index: 2;
        font-size: x-large;
        text-align: center;
    }
    .text-proposition-home {
        z-index: 2;
        text-align: center;
        line-height: 25px;
    }

    .button-home {
        z-index: 2;
        position: relative;

        cursor: pointer;

        height: 65px;
        width: 170px;

        display: flex;
        align-items: center;
        justify-content: center;
        gap: 7px;

        background-color: transparent;
        border: 2px solid #192767;

        border-radius: 9px;

        transition: all 125ms;
    }
    .button-home:hover,
    .button-home:focus {
        color: white;
        box-shadow:
            inset -5.5rem 0 0 0 #192767,
            inset 5.5rem 0 0 0 #192767;
    }
    .button-text-home {
        font-size: large;
        font-weight: bolder;
    }
    .button-image-home {
        width: 48px;
        height: 48px;
    }
    .button-home:hover,
    .button-home:focus > .button-image-home {
        content: url('/logo_white.svg');
    }

    .color-text {
        color: #192767;
    }
</style>

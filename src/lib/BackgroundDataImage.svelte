<script>
    import { onMount } from "svelte";
    let mounted = false;

    export let id;
    export let src;
    export let alt="";
    export let mouseOnMain;

    let backgroundDataImage;
    $: mouseOnMainEvent(mouseOnMain);

    // We need two conseguent position of mouse to calculate velocity of impact
    let prevMouseEvent;
    let currMouseEvent;
    let movementX;
    let movementY;
    let movement;
    let speed;
    let acceleration;
    let prevSpeed;
    function mouseOnMainEvent(e) {
        if (!mounted) {
            return;
        }
        currMouseEvent = e;
    }


    function mouseOnEnterEvent(e) {
        if (!mounted) {
            return;
        }

        // updateVector = [movementX, movementY]

        console.log(e);
        console.log(e.target.offsetWidth);
        console.log(e.target.offsetHeight);
        console.log(e.fromElement.offsetWidth); // parent
        console.log(e.fromElement.offsetHeight);

        let randomPositionX = Math.random() * (e.fromElement.offsetWidth - e.target.offsetWidth);
        let randomPositionY = Math.random() * (e.fromElement.offsetHeight - e.target.offsetHeight);

        console.log(randomPositionX)
        console.log(randomPositionY)

        e.target.style.left = randomPositionX + "px";
        e.target.style.top = randomPositionY + "px";
    }

    let updateVector = undefined;
    function update_element(e, updateVector) {
        if (!updateVector) {
            return;
        }

        let position = e.getBoundingClientRect();

        e.style.left = ((position.left + updateVector[0]) + "px");
        e.style.top = ((position.top + updateVector[1]) + "px");
    }

    onMount(()=> {
        mounted = true;

        // // Render three collisions: between elements, between element and boundaries, and between element and mouse
        // let renderer = setInterval(() => {
        //     if (prevMouseEvent && currMouseEvent) { 
        //         movementX = currMouseEvent.screenX - prevMouseEvent.screenX;
        //         movementY = currMouseEvent.screenY - prevMouseEvent.screenY;
        //         movement = Math.sqrt(movementX * movementX + movementY * movementY);
                
        //         // speed = movement/100ms = movement/0.1s = 10 * movement/s
        //         speed = 10 * movement; // current speed px/s
        //         acceleration= 10 * (speed - prevSpeed); // current acceleration px/s^2
        //     }

        //     update_element(backgroundDataImage, updateVector);
        //     updateVector = undefined

        //     prevMouseEvent = currMouseEvent
        //     prevSpeed = speed;
        // }, 100);
    })
</script>

<div class="background-data-image-container-home" {id} bind:this={backgroundDataImage} on:mouseenter={mouseOnEnterEvent}>
    <img class="background-data-image-home" {src} {alt}>
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
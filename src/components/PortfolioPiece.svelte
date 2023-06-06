<script>
    import { onMount } from "svelte";
    import { afterUpdate } from "svelte";
    import { goto } from '$app/navigation';


    // Props
    export let title = "Portfolio Piece";
    export let image = "https://picsum.photos/seed/picsum/2000/1000";
    export let scrollPos;
    export let number = "01";
    export let color = "BFC195";

    let speed = 0.15;
    let initialPos;
    let imgElement;
    let imgHeight;
    let division = 3;
    let offset = -500;

    onMount(() => {
        handleResize();
        window.addEventListener("resize", handleResize);
        // window.setTimeout(() => {
        //     handleResize();
        // }, 20);

        //Create a media query
        const mediaQuery = window.matchMedia("(max-width: 700px)");
        handleMediaQueryChange(mediaQuery); // Call listener function at run time
        mediaQuery.addEventListener("change", handleMediaQueryChange);

        return () => {
            // Cleanup function to remove the event listener when the component is unmounted
            mediaQuery.removeEventListener("change", handleMediaQueryChange);
        };
    });
    function handleMediaQueryChange(mediaQuery) {
        if (mediaQuery.matches) {
            // If the media query matches (screen width less than 700px)
            division = 3;
            offset = 100;
            speed = 0.1;
        } else {
            // If not
            division = 5;
            offset = -500;
        }
    }

    afterUpdate(() => {
        handleResize();
    });

    function handleResize() {
        initialPos = imgElement.getBoundingClientRect().top + window.scrollY;
        imgHeight = imgElement.getBoundingClientRect().height;
    }

    export let path = "/"
    function goToPage() {
        goto(path)
    }
</script>

<article>
    <div class="wrapper" style="background-color: {'#' + color};" on:click={goToPage(path)}>
        <div class="bg-img">
            <img
                bind:this={imgElement}
                src={image}
                alt="Banner"
                style:transform="translateY({(scrollPos - initialPos - imgHeight / division + offset) * - speed}px)"
            />
        </div>
        <div class="bg-gradient" />
        <section class="content">
            <h2>{title}</h2>
        </section>
    </div>
    <div class="flex">
        <h3>{number}</h3>
        <div>
            <h4>Mine roller</h4>
            <slot name="roles" />
        </div>
        <div>
            <h4>Teknologier</h4>
            <slot name="tech" />
        </div>
    </div>
</article>

<style>
    article {
        margin: var(--margin) var(--margin) calc(var(--margin) * 2)
            var(--margin);
    }

    .wrapper {
        position: relative;
        z-index: 1;
        overflow: hidden;
        border-radius: var(--border-radius);
        background-color: var(--card-color);
        cursor: pointer;
    }
    .bg-img {
        position: relative;
        overflow: hidden;
        width: 100%;
        aspect-ratio: 3 / 1.25;
        display: flex;
        align-items: center;
    }
    .bg-img img {
        width: 100%;
        object-fit: cover;
    }

    .content {
        position: absolute;
        z-index: 2;
        bottom: 0;
    }
    .flex {
        display: flex;
    }
    .content h2,
    h3 {
        margin: var(--card-margin) calc(var(--card-margin) * 2)
            var(--card-margin) var(--card-margin);
        font-size: 2.5em;
    }
    h3 {
        font-size: 1.75em;
        opacity: 0.3;
    }
    h2 {
        color: var(--white);
    }
    .flex div {
        margin-right: calc(var(--card-margin) * 2.5);
        font-weight: 500;
    }
    .flex div :global(p) {
        margin: 0;
        line-height: 1.5;
    }
    h4 {
        opacity: 0.3;
        margin: var(--card-margin) 0 0 0;
    }

    .bg-gradient {
        position: absolute;
        z-index: 0;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 50%;
        background: linear-gradient(
            180deg,
            rgba(0, 0, 0, 0) 0%,
            rgba(0, 0, 0, 0.05) 10%,
            rgba(0, 0, 0, 0.75) 100%
        );
    }

    @media only screen and (max-width: 768px) {
        .content h2, h3{
            font-size: 1.5em;
        }
        .bg-img {
        aspect-ratio: 3 / 1.75;
    }
    }
</style>

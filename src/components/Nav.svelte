<script>
    import { onMount } from "svelte";
    import { fade, fly } from 'svelte/transition';
    let menuOpen = false;
    let isMobile = false;
    let windowWidth;

    onMount(() => {
        handleResize();
    });

    function handleResize(){
        if(windowWidth >= 768) {
            menuOpen = false;
            isMobile = false;
        } else {
            isMobile = true;
        }
        console.log("width"+windowWidth);
    }

    function toggleMenu() {
        if (isMobile) menuOpen = !menuOpen;
    }
</script>

<svelte:window on:resize={handleResize} bind:innerWidth={windowWidth}/>

<nav>
    <a href="/" class="logo">Mattis Henner <span>Portfolio</span></a>
    <ul class={isMobile && menuOpen ? "open" : ""}>
        <li><a href="/om3" on:click={toggleMenu}>Om mig</a></li>
        <li><a href="/kontakt2" on:click={toggleMenu}>Kontakt</a></li>
        <li>
            <ul class="nested">
                <li><a href=""><img src="/img/github.svg" alt="" /></a></li>
                <li><a href=""><img src="/img/dribbble.svg" alt="" /></a></li>
                <li><a href=""><img src="/img/linkedin.svg" alt="" /></a></li>
            </ul>
        </li>
    </ul>
    <button class="menu-icon" on:click={toggleMenu}>
        <div class="placeholder">Menu</div>
        {#if menuOpen}
            <div class="ghost" transition:fly="{{y: -20, duration: 200}}">Luk</div>
        {:else}
            <div class="ghost" transition:fly="{{y: 20, duration: 200}}">Menu</div>
        {/if}
        
    </button>
</nav>

<style>
    .placeholder {
        visibility: hidden;
    }
    .ghost {
        position: absolute;
        top: 0;
        right: 0;
    }
    .menu-icon {
        border-radius: 0;
        border: none;
        background-color: transparent;
        font-size: 1em;
        display: none;
        position: relative;
    }
    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 5px var(--margin);
        font-weight: 500;
        position: sticky;
        top: 0;
        z-index: 900;
    }

    a {
        font-weight: 500;
    }

    nav ul {
        display: flex;
        list-style: none;
        align-items: center;
        padding: 0;
    }

    nav ul li {
        margin-left: var(--nav-spacing);
    }

    ul ul li:first-of-type {
        margin-left: 0;
    }

    nav ul li a,
    nav ul li a:visited,
    .logo {
        text-decoration: none;
        color: var(--black);
    }

    nav ul li a img {
        border-radius: 50%;
    }

    .logo {
        font-size: 1em;
    }
    .logo span {
        opacity: 0.3;
    }

    /* SoMe icons */
    ul ul li {
        margin-left: calc(var(--nav-spacing) / 2);
        opacity: 0.2;
        transition: all 0.2s ease-in-out;
    }
    ul ul li:hover {
        opacity: 1;
        transform: scale(1.1) rotate(10deg);
    }

    /* Underline hover effect */
    nav ul:not(.nested) > li > a,
    .logo {
        position: relative;
    }
    nav ul:not(.nested) > li > a:after,
    .logo:after {
        position: absolute;
        bottom: -2px;
        left: 0;
        margin: auto;
        width: 0%;
        content: ".";
        color: transparent;
        background: var(--black);
        height: 2px;
        transition: all 0.2s ease-in-out;
    }
    nav ul:not(.nested) > li > a:hover:after,
    .logo:hover:after {
        width: 1.5em;
    }

    @media only screen and (max-width: 768px) {
        nav {
            padding: 20px var(--margin);
        }
        .menu-icon {
            display: block;
            cursor: pointer;
            z-index: 999;
        }
        nav > ul {
            flex-direction: column;
            background-color: var(--white);
            position: absolute;
            left: 0;
            right: 0;
            top: 0;
            margin: 0;
            min-height: 50dvh;
            justify-content: center;
            z-index: 998;
            box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.05);
            transform: translateY(-100%);
            transition: all 0.2s ease-out;
        }
        nav > ul.open {
            transform: translateY(0%);
        }
        nav > ul > li {
            margin: 20px;
        }
    }
</style>

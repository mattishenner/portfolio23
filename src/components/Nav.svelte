<nav>
    <a href="/" class="logo">Mattis Henner <span>Portfolio</span></a>
    <ul>
        <li><a href="/om">Om mig</a></li>
        <li><a href="">Kontakt</a></li>
        <li>
            <ul class="nested">
                <li><a href=""><img src="/img/github.svg" alt="" /></a></li>
                <li><a href=""><img src="/img/dribbble.svg" alt="" /></a></li>
                <li><a href=""><img src="/img/linkedin.svg" alt="" /></a></li>
            </ul>
        </li>
    </ul>
</nav>

<style>
    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 5px var(--margin);
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
</style>

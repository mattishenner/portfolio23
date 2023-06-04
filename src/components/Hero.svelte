<header>
    <img src="/img/portrait.jpeg" alt="portræt af Mattis">
    <h1>
        Hey, jeg er Mattis. <br />
        Udvikler, designer og specialist i, <span class="mobile-break"></span>
        at skrælle det unødvendige væk.
    </h1>
</header>


<style>
    header{
        display: flex;
        align-items: center;
        gap: var(--nav-spacing);
        justify-content: center;
        min-height: 50dvh;
        margin: 0 var(--margin);
    }
    img{
        max-width: 97px;
        aspect-ratio: 1 / 1;
        object-fit: cover;
        border-radius: 28px;
    }
    h1{
        font-size: 1.5em;
    }
    .mobile-break::after {
        content: '\A';
        white-space: pre;
    }

    @media only screen and (max-width: 600px) {
    header{
        flex-direction: column;
        gap: 0;

        align-items: center;
        text-align: center;
        min-height: 70dvh;
    }
    img{
        max-width: 68px;
        border-radius: 22px;
    }
    .mobile-break::after {
        content: '';
        white-space: pre;
    }
}

</style>
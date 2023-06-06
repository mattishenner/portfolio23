<script>
    export let text = "Knowing that inspiration is an open mind; originality allows us to grow."
</script>

<header>
    <h1>
        {text}
    </h1>
    <div class="slot">
        <slot />
    </div>
</header>


<style>
    header{
        display: flex;
        flex-direction: column;
        justify-content: center;
        min-height: 50dvh;
        margin: 0 var(--margin);
    }
    h1{
        font-size: 1.5em;
        max-width: 500px;
        margin-left: clamp(30px, 10dvw, 300px);
        margin-right: var(--margin);
    }
    .slot{
        margin-left: clamp(30px, 10dvw, 300px);
        margin-right: var(--margin);
        font-size: 16px;
    }
    h1::before{
        content: '';
        border-left: 8px solid var(--green);
        margin-right: 8px;
        margin-left: 48px;
        border-radius: var(--border-radius);
    }

    @media only screen and (max-width: 768px) {
        h1{
            margin-left: 8%;
            max-width: 70%;
        }
        .slot{
            margin-left: 8%;
        }
    }
</style>
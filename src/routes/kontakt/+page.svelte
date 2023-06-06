<script>
    import Contact from "../../components/Contact.svelte";
</script>


<article>
    <section>
        <h2>Kontakt mig titel hihi. Earum quam rem dolore voluptatum</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse quidem id eius inventore. Laboriosam, saepe?</p>
        <ul>
            <li><a href="/">+45 81 72 41 42</a></li>
            <li><a href="/">hej@mattishenner.dk</a></li>
        </ul>
    </section>

    <Contact />
</article>

<style>
    ul{
        list-style: none;
        padding: 0;
        margin: 0;
    }
    li{
        margin-bottom: 1rem;
    }
    h2::before{
        content: '';
        border-left: 8px solid var(--green);
        margin-right: 8px;
        margin-left: 48px;
        border-radius: var(--border-radius);
    }
    article{
        display: grid;
        grid-template-columns: 2fr 3fr;
        margin: 80px var(--margin);
        gap: var(--margin);
    }
    h2{
        font-size: 1.75em;
        margin-top: 0;
        margin-bottom: 0;
    }
    @media only screen and (max-width: 768px){
        article{
            grid-template-columns: 1fr;
            margin-top: 60px;
        }
        section{
            margin-bottom: 60px;
        }
    }
</style>
<script>
    import Contact from "../../components/Contact.svelte";
    import HeroGen from "../../components/HeroGen.svelte";
</script>

<HeroGen > 
    <ul>
        <li><a href="">+45 81 72 41 42</a></li>
        <li><a href="">hej@gmail.com</a></li>
    </ul>
</HeroGen>

<article>
    <Contact />
</article>

<style>
    ul{
        list-style: none;
        padding: 0;
        margin: 0;
    }
    li{
        margin-top: .5rem;
    }
    h2::before{
        content: '';
        border-left: 8px solid var(--green);
        margin-right: 8px;
        margin-left: 48px;
        border-radius: var(--border-radius);
    }
    article{
        display: flex;
        justify-content: center;
        background-color: var(--green);
        padding-top: 40px;
        padding-bottom: 40px;
    }
    h2{
        font-size: 1.75em;
        margin-top: 0;
        margin-bottom: 0;
    }
    @media only screen and (max-width: 768px){
        section{
            margin-bottom: 60px;
        }
    }
</style>
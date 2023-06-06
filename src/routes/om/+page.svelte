<script>
    import HeroGen from "../../components/HeroGen.svelte";
</script>


<HeroGen />



<section class="cols">
    <img src="/img/portrait2.png" alt="portræt af Mattis">
    <div class="p1">
        <h2>Her er lidt om mig hehe</h2>
        <p>
            Founded in 2015 by partners Nicolas Fuhr, creative director, and Julie Fuhr, identity designer, Fuhr Studio is a design and branding studio based in Denmark.
        </p>
        <p>
            As a strategic studio, we’re greatly aware of the powers of design; its ability to make people notice – anything.
        </p>
        <p>
            With absolute commitment to change for the better, we wield that power.
        </p>
    </div>
    <div class="spacer"></div>
    <div>
        <div class="line"></div>
    </div>
    <div>
        <h2>Her er lidt om mig hehe</h2>
        <p>We choose new behaviour over new design, striving for radical transformation through bold, high-quality craftmanship – not the other way around.</p>
    </div>
    <div>
        <h2>Her er lidt om mig hehe</h2>
        <p>We choose new behaviour over new design, striving for radical bold, high-quality craftmanship – not the other way around.</p>
    </div>
    <div>
        <h2>Her er lidt om mig hehe</h2>
        <p>We choose new behaviour over new design, striving for radical transformation bold, high-quality craftmanship – not the other way around.</p>
    </div>
</section>


<style>
    h2{
        font-size: 1.5em;
        margin-top: 0;
        margin-bottom: 1rem;
    }
    section{
        margin: 0 var(--margin);
    }

    .p1{
        grid-column: span 3;
        margin-top: auto;
        margin-bottom: auto;
    }

    img{
        width: 100%;
        border-radius: calc(var(--border-radius) * 0.5);
        min-width: 240px;
    }

    .spacer{
        height: 10px;
        grid-column: span 4;
    }
/* 
    .p1{
        grid-column: span 3;
        margin-top: auto;
        margin-bottom: auto;
    } */

    .p1 :last-child{
        margin-bottom: 0;
    }

    .cols{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        gap: var(--margin);
    }
    .cols h2{
        margin-top: -6px;
    }
    .line{
        border-top: 8px solid var(--green);
        margin-bottom: 20px;
        border-radius: var(--border-radius);
    }

    @media only screen and (max-width: 768px){
        .container{
            display: flex;
            flex-direction: column-reverse;
            align-items: start;
            padding: 20px;
        }

        .container img{
            margin-top: 10px;
            width: 100%;
            aspect-ratio: 3 / 2;
            object-fit: cover;
        }

        .cols{
            grid-template-columns: 1fr;
        }
        h2 {
            margin-bottom: 0;
        }
    }
</style>
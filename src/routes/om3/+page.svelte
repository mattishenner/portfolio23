<script>
    import HeroGen from "../../components/HeroGen.svelte";
</script>


<HeroGen />





<section class="cols">
    <div class="container">
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
    </div>
    <div class="spacer"></div>
    <div>
        <div class="line"></div>
    </div>
    <div class="mb">
        <h2>Her er lidt om mig hehe</h2>
        <p>We choose new behaviour over new design, striving for radical transformation through bold, high-quality craftmanship – not the other way around.</p>
    </div>
    <div class="mb">
        <h2>Her er lidt om mig hehe</h2>
        <p>We choose new behaviour over new design, striving for radical bold, high-quality craftmanship – not the other way around.</p>
    </div>
    <div class="mb">
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

    .container{
        grid-column: span 4;
        display: grid;
        grid-template-columns: 1fr 3fr;
        background-color: var(--green);
        align-items: center;
        gap: var(--margin);
        padding: var(--margin);
        border-radius: 0;
        margin-left: calc(-1 * var(--margin));
        margin-right: calc(-1 * var(--margin));
    }

    img{
        width: 100%;
        border-radius: calc(var(--border-radius) * 0.75);
        min-width: 240px;
    }
    .line-short{
        border-top: 8px solid var(--green);
        border-radius: var(--border-radius);
        width: 50px;
    }
    .spacer{
        height: 10px;
        grid-column: span 4;
    }
    .mb{
        margin-bottom: 40px;
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
            flex-direction: column;
            align-items: center;
            padding: 30px 10px;
            /* background-color: transparent; */
            margin-bottom: 20px;
        }

        .container h2{
            text-align: center;
        }

        .container img{
            margin-bottom: 10px;
            width: 96px;
            min-width: 96px;
        }

        .line{
            display: none;
        }

        .cols{
            display: block;
        }
        h2 {
            margin-bottom: 0;
        }

    }
</style>
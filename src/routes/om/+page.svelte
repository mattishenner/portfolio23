<script>
    import HeroAbout from "../../components/HeroAbout.svelte";
</script>


<HeroAbout />

<section class="top">
    <img src="/img/portrait2.png" alt="portræt af Mattis">
    <div>
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
</section>

<section class="cols">
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
    }
    section{
        margin: 0 var(--margin);
    }

    .top{
        display: grid;
        grid-template-columns: 1fr 2fr;
        gap: calc(var(--margin) * 2);
        height: fit-content;
        margin-bottom: 64px;
        align-items: center;
    }
    .top img{
        width: 100%;
        border-radius: calc(var(--border-radius) * 2);

    }

    .top div{
        position: relative;
        background-color: var(--white);
        padding: 0 0 calc(var(--margin) / 2) calc(var(--margin) / 2);
        border-radius: var(--border-radius);

    }
    .top div :last-child{
        margin-bottom: 0;
    }

    .top div:after{
        content: "";
        display: block;
        width: 100%;
        height: 100%;
        position: absolute;
        top: var(--margin);
        right: var(--margin);
        background-color: var(--green);
        z-index: -1;
        border-radius: var(--border-radius);
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
        border-top: var(--margin) solid var(--green);
        margin-bottom: 20px;
        border-radius: var(--border-radius);
    }

    @media only screen and (max-width: 768px){
        .top{
            display: flex;
            flex-direction: column-reverse;
            margin-bottom: 30px;
        }
        .top div{
            margin-left: var(--margin);
        }
        .top img{
            width: 100%;
            aspect-ratio: 3 / 2.25;
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
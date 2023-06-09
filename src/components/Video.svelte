<script>
    export let path = "/"
    export let color = "fff"
</script>

<div class="vid" style="background-color: {"#" + color};">
    <video src={path} muted autoplay loop></video>
</div>

<style>
    .vid{

        display: flex;
        align-items: center;
        justify-content: center;
        padding: 40px var(--margin);
    }
    video{
        max-width: 1000px;
        width: 100%;
        border-radius: var(--border-radius);
        box-shadow: 0px 0px 35px rgba(0,0,0,0.15);
    }
</style>
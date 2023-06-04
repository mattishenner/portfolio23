<script>
    import { page } from '$app/stores';
    import { fly } from 'svelte/transition';
    import '../app.css';
    import Nav from '../components/Nav.svelte';
    export let data;
</script>

<main>
    <Nav />
    {#key data.url}
        <div 
            in:fly={{y: -20, duration: 500, delay: 500}}
            out:fly={{y: 20, duration: 500}}
            >
            <slot />
        </div>
    {/key}
</main>
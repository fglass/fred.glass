<script>
    import ContentPage from "./ContentPage.svelte";
    import { Splide, SplideSlide } from '@splidejs/svelte-splide';
    import '@splidejs/svelte-splide/css';
    const cards = [
        { src: "sailing.gif", title: "Sailing" },
        { src: "construction.png", title: "Construction" },
        { src: "interface.gif", title: "Interface" },
        { src: "plugins.gif", title: "Plugins" },
        { src: "models.png", title: "Models" },
    ];
</script>

<svelte:head>
    <title>fred.glass · Dragonfire</title>
</svelte:head>

<ContentPage image="dragonfire/logo.gif">
    <p class="lead">An Old School RuneScape (OSRS) emulation created for educational purposes</p>
    <h2>Features</h2>
    <ul>
        <li>All prominent OSRS content implemented</li>
        <li>Custom Sailing skill</li>
        <li>Sims-esque Construction skill</li>
        <li>Procedurally generated islands</li>
        <li>Hot reloadable Kotlin plugins</li>
        <li>Bespoke 3D models</li>
    </ul>
    <h2>Media</h2>
    <Splide aria-label="Media">
        {#each cards as card}
            <SplideSlide>
                <img src={`dragonfire/${card.src}`} alt={card.title}/>
            </SplideSlide>
        {/each}
    </Splide>
</ContentPage>

<style>
    img {
        width: 100%;
    }
</style>
<script>
    import ContentPage from "./ContentPage.svelte";
    import { Splide, SplideSlide } from '@splidejs/svelte-splide';
    import '@splidejs/svelte-splide/css';
    const cards = [
        { src: "dab.gif", title: "Dab" },
        { src: "dragon.png", title: "Dragon" },
        { src: "wave.gif", title: "Wave" },
        { src: "drink.png", title: "Drink" },
    ];
</script>

<svelte:head>
    <title>fred.glass · PoserGL</title>
</svelte:head>

<ContentPage image="posergl.png">
    <p class="lead">A RuneScape animation editor, written in Kotlin and rendered using OpenGL</p>
    <h2>Features</h2>
    <ul>
        <li>3D editing gizmos: translation, rotation, scale</li>
        <li>Keyframe editing: adding, copying, pasting, interpolating, deleting</li>
        <li>Animation exporting (custom & proprietary formats)</li>
        <li>Composite model support with item equipping</li>
        <li>Resizable UI with a dynamic animation timeline</li>
        <li>Selectable polygon modes & shading types</li>
        <li>Custom keybindings</li>
        <li>Undo and redo</li>
        <li>Extensible plugin system</li>
        <li><a href="https://github.com/fglass/poser-gl">Open source</a></li>
    </ul>
    <h2>Media</h2>
    <Splide aria-label="Media">
        {#each cards as card}
            <SplideSlide>
                <img src={`posergl/${card.src}`} alt={card.title}/>
            </SplideSlide>
        {/each}
    </Splide>
</ContentPage>

<style>
    span {
        float: right;
    }
    img {
        width: 100%;
    }
</style>
<script>
    import ContentPage from "../ContentPage.svelte";
    import ImageSlider from "../ImageSlider.svelte";
    const images = [
        { src: "dragonfire/sailing.gif", label: "Sailing" },
        { src: "dragonfire/construction.png", label: "Construction" },
        { src: "dragonfire/interface.gif", label: "Interface" },
        { src: "dragonfire/plugins.gif", label: "Plugins" },
        { src: "dragonfire/models.png", label: "Models" },
    ];
</script>

<svelte:head>
    <title>fred.glass · Dragonfire</title>
</svelte:head>

<ContentPage image="dragonfire/logo.gif">
    <p>An Old School RuneScape (OSRS) emulation created for educational purposes</p>
    <h2>Features</h2>
    <ul>
        <li>All prominent OSRS content implemented</li>
        <li>Sims-esque Construction skill</li>
        <li>Custom Sailing skill</li>
        <li>Procedurally generated islands</li>
        <li>Hot reloadable content plugins</li>
        <li>Unique minigames</li>
        <li>Bespoke 3D models</li>
    </ul>
    <h2>Media</h2>
    <ImageSlider images={images} />
</ContentPage>

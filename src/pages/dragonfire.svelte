<script>
    import ContentPage from "../ContentPage.svelte";
    import ImageSlider from "../ImageSlider.svelte";
    const images = [
        { src: "dragonfire/construction.gif", label: "Construction" },
        { src: "dragonfire/sailing.gif", label: "Sailing" },
        { src: "dragonfire/generation.gif", label: "Map Generation" },
        { src: "dragonfire/mystery.gif", label: "Mystery Box" },
        { src: "dragonfire/wheel.gif", label: "Wheel of Fortune" },
    ];
</script>

<svelte:head>
    <title>fred.glass · Dragonfire</title>
</svelte:head>

<ContentPage 
    image="dragonfire/logo.gif" 
    --img-max-width="500px" 
    --img-aspect-ratio="500 / 470"
>
    <p>An Old School RuneScape (OSRS) emulation created for educational purposes</p>
    <h2>Features</h2>
    <ul>
        <li>All prominent OSRS content</li>
        <li>Sims-esque Construction</li>
        <li>Custom Sailing skill</li>
        <li>Procedurally generated islands</li>
        <li>Hot reloadable content plugins</li>
        <li>Bespoke 3D models</li>
        <li>Unique minigames</li>
    </ul>
    <h2>Media</h2>
    <ImageSlider images={images} />
</ContentPage>
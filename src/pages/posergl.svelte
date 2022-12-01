<script>
    import ContentPage from "../ContentPage.svelte";
    import ImageSlider from "../ImageSlider.svelte";
    const images = [
        { src: "posergl/dab.gif", label: "Dab" },
        { src: "posergl/dragon.png", label: "Dragon" },
        { src: "posergl/wave.gif", label: "Wave" },
        { src: "posergl/drink.png", label: "Drink" },
    ];
</script>

<svelte:head>
    <title>fred.glass · PoserGL</title>
</svelte:head>

<ContentPage image="posergl.png">
    <p>A RuneScape animation editor, written in Kotlin and rendered using OpenGL</p>
    <h2>Features</h2>
    <ul>
        <li>Keyframe editing: adding, copying, pasting, interpolating, deleting</li>
        <li>3D editing gizmos: translation, rotation, scale</li>
        <li>Animation exporting: custom & proprietary formats</li>
        <li>Composite model support with item equipping</li>
        <li>Resizable UI with a dynamic animation timeline</li>
        <li>Selectable polygon modes & shading types</li>
        <li>Custom keybindings</li>
        <li>Undo and redo</li>
        <li>Extensible plugin system</li>
        <li><a href="https://github.com/fglass/poser-gl">Open source</a></li>
    </ul>
    <h2>Media</h2>
    <ImageSlider images={images} />
</ContentPage>

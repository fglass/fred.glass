<script>
    const cards = [
        { src: "construction.png", title: "Reimagined Construction" },
        { src: "sailing.gif", title: "New Sailing Skill" },
        { src: "map.png", title: "Dynamic World Map" },
        { src: "interface.gif", title: "Replicated Interfaces" },
        { src: "models.png", title: "Bespoke Models" },
        { src: "plugins.gif", title: "Hot Reloadable Plugins" },
    ];
</script>

<svelte:head>
    <title>fred.glass · Dragonfire</title>
</svelte:head>

<div class="container" >
    <img class="img" src="dragonfire.gif" alt="Dragonfire">
    <h1 class="header pt-3">
        An <a href="https://oldschool.runescape.com">Old School RuneScape</a> Emulation
    </h1>
    <p class="lead text-muted pt-1">
        Multi-threaded client-server Java application with an extensible Kotlin plugin system
    </p>
    <img class="img pt-4" src="dragonfire/client.png" alt="Client"/>
</div>

 <div class="album mt-5 py-5 bg-light" style="background:#353a3f !important">
    <div class="container">
        <div class="row">
            {#each cards as card}
                <div class="col-md-4">
                    <div class="card text-white mb-4 shadow-sm">
                        <img class="card-img-top" src={`dragonfire/${card.src}`} alt={card.title}>
                        <div class="card-body">
                            <h5 class="card-title">{card.title}</h5>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
    </div>
</div>

<style>
    .header {
        color: #a0afbc;
    }

    .card {
        border: 0;
        background-color: #282b2e;
    }
</style>
<svelte:head>
    <title>fred.glass · Housyn</title>
</svelte:head>

<script>
    import WaveSurfer from "wavesurfer.js";
    import { onMount } from "svelte";

    const trackLabels = [
        "Final Product: Multi-Instrument MIDI",
        "Prototype #2: Waveform Operation",
        "Prototype #1: Beethoven"
    ];

    let wavesurfer = null
    let trackIndex = 0;

    onMount(() => {
        wavesurfer = WaveSurfer.create({
            container: "#waveform",
            waveColor: "white",
            progressColor: "grey",
            barWidth: 2,
        });

        wavesurfer.on("play", function () {
            document.getElementById("play").src = getResource("pause.svg")
        });

        wavesurfer.on("pause", function () {
            document.getElementById("play").src = getResource("play.svg")
        });
    })

    $: {
        if (wavesurfer != null) {
            wavesurfer.load(getResource(`track${trackIndex}.mp3`));
        }
    }

    function changeTrack(next) {
        trackIndex = mod(trackIndex, trackLabels.length, next ? 1 : -1);
    }

    function mod(n, m, delta) {
        return (((n + delta) % m) + m) % m;
    }

    function getResource(name) {
        return `housyn/${name}`
    }
</script>

<div class="container">
    <div class="row">
        <div class="col text-secondary">
            <img class="img" src="housyn.png" alt="Housyn" />
            <h1 class="text-light">Housyn</h1>
            <p>
                Algorithmic generation of house music<br>
            </p>
        </div>
    </div>

    <div id="waveform"></div>
    <p class="text-secondary" id="name">{trackLabels[trackIndex]}</p>
    <input type="image" src={getResource("previous.svg")} width="46" alt="Previous" on:click={() => changeTrack(false)} />
    <input type="image" id="play" src={getResource("play.svg")} width="46" alt="Play" on:click={() => wavesurfer.playPause()} />
    <input type="image" src={getResource("next.svg")} width="46" alt="Next" on:click={() => changeTrack(true)} />
</div>

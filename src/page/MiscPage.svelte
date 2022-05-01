<script>
    import RepoCard from "svelte-repo-card";

    const theme = {
        text: "#8b949e",
        link: "#0366d6",
        background: "#343a40",
        border: "#30363d",
    }
</script>

<svelte:head>
    <title>fred.glass · Misc</title>
</svelte:head>

<div class="container">
    <h1 class="text-light">Miscellaneous</h1>
    <p class="lead text-secondary">
        A collection of small, experimental projects created for fun or to solve a problem
    </p>
    <div class="cards mt-4">
        <RepoCard slug="fglass/readunwise" theme={theme} />
        <RepoCard slug="fglass/obsidx" theme={theme} />
        <RepoCard slug="fglass/advent-of-code" theme={theme} />
    </div>
</div>

<style>
    .cards {
        display: grid;
        grid-template-columns: 1fr 1fr;
        column-gap: 1.5em;
        row-gap: 1.5em;
    }

    @media screen and (max-width: 768px) {
        .cards {
            grid-template-columns: auto;
            row-gap: 1em;
        }
    }
</style>
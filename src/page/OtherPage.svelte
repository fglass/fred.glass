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
    <h1 class="text-light">Other Projects</h1>
    <div class="cards">
        <RepoCard slug="fglass/readunwise" theme={theme} />
        <RepoCard slug="fglass/obsidx" theme={theme} />
        <RepoCard slug="fglass/advent-of-code" theme={theme} />
    </div>
</div>

<style>
    .cards {
        margin-top: 2.5em;
        display: grid;
        grid-template-columns: 1fr 1fr;
        column-gap: 1.5em;
        row-gap: 1.5em;
    }
</style>

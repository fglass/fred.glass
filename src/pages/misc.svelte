<script>
    import ContentPage from "../ContentPage.svelte";
</script>

<svelte:head>
    <title>fred.glass · Misc</title>
</svelte:head>

<ContentPage title="Miscellaneous">
    <p class="subheading">A collection of small, experimental projects created for fun or to solve a problem:</p>
    <ul>
        <li><a href="https://github.com/fglass/inelastic">inelastic</a>: in-memory full-text search engine</li>
        <li><a href="https://github.com/fglass/bloog">bloog</a>: search engine for technical blogs</li>
        <li><a href="https://github.com/fglass/readunwise">readunwise</a>: CLI for managing Kindle highlights</li>
        <li><a href="https://github.com/fglass/advent-of-code">advent-of-code</a>: incomplete collection of unpolished solutions for <a href="https://adventofcode.com">Advent of Code</a></li>
    </ul>
</ContentPage>

<style>
    .subheading {
        margin-bottom: 0;
    }
</style>
<script>
    import ContentPage from "../ContentPage.svelte";
</script>

<svelte:head>
    <title>fred.glass · Misc</title>
</svelte:head>

<ContentPage title="Miscellaneous">
    <p class="subheading">A collection of small, experimental projects created for fun or to solve a problem:</p>
    <ul>
        <li><a href="https://github.com/fglass/bloog">bloog</a>: search engine for technical blogs</li>
        <li><a href="https://github.com/fglass/readunwise">readunwise</a>: CLI for managing Amazon Kindle highlights</li>
        <li><a href="https://github.com/fglass/obsidx">obsidx</a>: quick launcher for markdown files in <a href="https://obsidian.md">Obsidian</a> vaults</li>
    </ul>
</ContentPage>

<style>
    .subheading {
        margin-bottom: 0;
    }
</style>
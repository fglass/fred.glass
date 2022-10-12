<script>
    // import RepoCard from "svelte-repo-card";
    import ContentPage from "./ContentPage.svelte";

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

<ContentPage title="Miscellaneous">
    <h2 >## Projects</h2>
    <ul>
        <li>readunwise</li>
        <li>obsidx</li>
        <li>advent-of-code</li>
    </ul>
    <h2>## Reading</h2>
    2022
    <ul>
        <li>Pragmatic Programmer<span>⭐️⭐️</span>️️</li>
        <li>Atomic Habits<span>⭐️⭐️⭐️⭐️</span></li>
        <li>Finish: Give Yourself the Gift of Done<span>️⭐️</span>️️</li>
        <li>Clean Code<span>⭐️⭐️⭐️⭐️</span></li>
        <li>Designing Data-Intensive Applications<span>⭐️⭐️⭐️⭐️⭐️</span></li>
        <li>How Life Imitates Chess<span>⭐️⭐️</span></li>
        <li>Cracking the Coding Interview<span>⭐️⭐️⭐️</span></li>
        <li>Architecture Patterns with Python<span>⭐️⭐️⭐️</span></li>
        <li>How to Solve It<span>⭐️⭐️⭐️</span></li>
    </ul>
    2021
        <ul>
        <li>Pragmatic Programmer<span>⭐️⭐️</span>️️</li>
        <li>Atomic Habits<span>⭐️⭐️⭐️⭐️</span></li>
        <li>Finish: Give Yourself the Gift of Done<span>️⭐️</span>️️</li>
        <li>Clean Code<span>⭐️⭐️⭐️⭐️</span></li>
        <li>Designing Data-Intensive Applications<span>⭐️⭐️⭐️⭐️⭐️</span></li>
        <li>How Life Imitates Chess<span>⭐️⭐️</span></li>
        <li>Cracking the Coding Interview<span>⭐️⭐️⭐️</span></li>
        <li>Architecture Patterns with Python<span>⭐️⭐️⭐️</span></li>
        <li>How to Solve It<span>⭐️⭐️⭐️</span></li>
    </ul>
</ContentPage>

<!--<div class="container">-->
<!--    <h1 class="text-light">Miscellaneous</h1>-->
<!--    <p class="lead text-secondary">-->
<!--        A collection of small, experimental projects created for fun or to solve a problem-->
<!--    </p>-->
<!--    <div class="cards mt-4">-->
<!--        <RepoCard slug="fglass/readunwise" theme={theme} />-->
<!--        <RepoCard slug="fglass/obsidx" theme={theme} />-->
<!--        <RepoCard slug="fglass/advent-of-code" theme={theme} />-->
<!--    </div>-->
<!--</div>-->

<style>
    span {
        float: right;
    }
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
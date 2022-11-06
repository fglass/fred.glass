<script>
    import ContentPage from "./ContentPage.svelte";
</script>

<svelte:head>
    <title>fred.glass · Misc</title>
</svelte:head>

<ContentPage title="Miscellaneous">
    <h2>Projects</h2>
    <p class="subheading">A collection of small, experimental projects created for fun or to solve a problem</p>
    <ul>
        <li><a href="https://github.com/fglass/readunwise">readunwise</a>: CLI for managing Amazon Kindle highlights</li>
        <li><a href="https://github.com/fglass/obsidx">obsidx</a>: quick launcher for markdown files in <a href="https://obsidian.md">Obsidian</a> vaults</li>
        <li><a href="https://github.com/fglass/advent-of-code">advent-of-code</a>: incomplete collection of unpolished solutions for <a href="https://adventofcode.com">AoC</a></li>
    </ul>
    <h2>Reading</h2>
    2022
    <table>
        <tr><td class="book">Pragmatic Programmer</td><td class="rating">⭐⭐</td></tr>
        <tr><td class="book">Atomic Habits</td><td class="rating">⭐⭐⭐⭐</td></tr>
        <tr><td class="book">Finish: Give Yourself the Gift of Done</td><td class="rating">⭐</td></tr>
        <tr><td class="book">Clean Code</td><td class="rating">⭐⭐⭐⭐</td></tr>
        <tr><td class="book">Designing Data-Intensive Applications</td><td class="rating">⭐⭐⭐⭐⭐</td></tr>
        <tr><td class="book">How Life Imitates Chess</td><td class="rating">⭐⭐</td></tr>
        <tr><td class="book">Cracking the Coding Interview</td><td class="rating">⭐⭐⭐</td></tr>
        <tr><td class="book">Architecture Patterns with Python</td><td class="rating">⭐⭐⭐</td></tr>
        <tr><td class="book">How to Solve It</td><td class="rating">⭐⭐⭐</td></tr>
    </table>
    2021
        <table>
            <tr><td class="book">Thinking, Fast and Slow</td><td class="rating">⭐⭐</td></tr>
            <tr><td class="book">The Stand</td><td class="rating">⭐⭐⭐⭐⭐</td></tr>
            <tr><td class="book">How to Win Friends and Influence People</td><td class="rating">⭐⭐⭐⭐</td></tr>
            <tr><td class="book">Happy Sexy Millionaire</td><td class="rating">⭐</td></tr>
            <tr><td class="book">Never Split the Difference</td><td class="rating">⭐⭐⭐⭐</td></tr>
            <tr><td class="book">Animal Farm</td><td class="rating">⭐⭐⭐⭐⭐</td></tr>
            <tr><td class="book">1984</td><td class="rating">⭐⭐⭐⭐</td></tr>
            <tr><td class="book">Deep Work</td><td class="rating">⭐⭐⭐⭐</td></tr>
            <tr><td class="book">Game Programming Patterns</td><td class="rating">⭐⭐⭐</td></tr>
            <tr><td class="book">Surely You're Joking Mr. Feynman</td><td class="rating">⭐⭐⭐</td></tr>
            <tr><td class="book">Ready Player One</td><td class="rating">⭐⭐⭐⭐⭐</td></tr>
            <tr><td class="book">Ready Player Two</td><td class="rating">⭐⭐</td></tr>
            <tr><td class="book">The 4-Hour Work Week</td><td class="rating">⭐⭐⭐</td></tr>
            <tr><td class="book">Dune Messiah</td><td class="rating">⭐⭐⭐</td></tr>
    </table>
</ContentPage>

<style>
    .subheading {
        margin-bottom: 0;
    }
    table {
        width: 100%;
    }
    .book {
        margin-left: 32px;
        display: list-item;
        text-align: left;
    }
    .rating {
        text-align: right;
        vertical-align: top;
    }
</style>
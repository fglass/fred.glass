<script>
    const nHexagons = Array(21)
    const hexagons = {
        10: { src: "dragonfire-logo.gif" },
        17: { src: "dragonfire-logo.gif" },
        11: { src: "dragonfire-logo.gif" },
        4: { src: "dragonfire-logo.gif" },
        12: { src: "dragonfire-logo.gif" },
    }
</script>

<div class="grid">
    <ul class="list">
        {#each nHexagons as _, i}
            <li class="item">
                <div class="content">
                    <div class="outer">
                        {#if i in hexagons}
                            <a href="/">
                                <div class="inner">
                                    <img src={hexagons[i].src} width="150" alt="Project" />
                                </div>
                            </a>
                        {/if}
                    </div>
                </div>
            </li>
        {/each}
    </ul>
</div>

<style lang="scss">
    $amount: 7;
    $outline-colour: rgb(52, 58, 64);
    $outer-colour: rgb(40, 43, 46);
    $inner-colour: rgb(52, 58, 64);
    $clip-path: polygon(75% 0, 100% 50%, 75% 100%, 25% 100%, 0 50%, 25% 0);

    img {
        max-width:100%;
        height:auto;
    }

    .grid {
        height: 100%;
        width: 70%;
        margin: 100px auto;
    }

    .list {
        --counter: 1;
        display: grid;
        list-style-type: none;
        margin: 0;
        padding: 0;
        grid-template-columns: repeat($amount, 1fr 2fr) 1fr;
        //grid-gap: 1rem 2rem;
    }

    .item {
        position: relative;
        grid-column: 1 / span 3;
        grid-row: calc(var(--counter) + var(--counter)) / span 2;
        height: 0;
        padding-bottom: 90%;

        // Columns
        @for $i from 1 through $amount {
            &:nth-of-type(#{$amount}n + #{$i}) {
                grid-column: #{$i + $i - 1} / span 3;
                @if $i % 2 == 0 {
                    grid-row: calc(var(--counter) + var(--counter) - 1) / span 2;
                }
            }
        }

        // Rows
        @for $i from 1 through 20 {
            &:nth-of-type(n + #{$i * $amount + 1}) {
                --counter: #{$i + 1};
            }
        }

        $ignored: 3, 8, 9, 10, 6, 14, 19;
        @each $i in $ignored {
            &:nth-of-type(#{$i}) {
                display: none;
            }
        }
    }

    .content {
        position: absolute;
        left: 0;
        top: 0;
        height: 100%;
        width: 100%;
        background-color: $outline-colour;
        clip-path: $clip-path;
        padding: 1px 1px;
    }

    .outer {
        height: 100%;
        width: 100%;
        background-color: $outer-colour;
        clip-path: $clip-path;
        padding: 10px 10px;
    }

    .inner {
        height: 100%;
        width: 100%;
        background-color: $inner-colour;
        clip-path: $clip-path;
        padding: 10px 0;
        transition: all .3s ease-in-out;
    }

    .inner:hover {
        transform: scale(1.15);
    }
</style>
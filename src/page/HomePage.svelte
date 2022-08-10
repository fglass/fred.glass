<script>
    const gitHubLink = "https://github.com/fglass"
    const items = [
        { src: "posergl.png", href: `${gitHubLink}/poser-gl`, width: 60 },
        { src: "dragonfire.png", href: "/dragonfire", width: 67 },
        { src: "stick-school.png", href: `${gitHubLink}/stick-school`, width: 60 },
        { src: "classesgg.png", href: "https://classes.gg/", width: 35 },
        { src: "portrait.png", href: "/about", width: 100 },
        { src: "puzzle.png", href: "/misc", width: 35 },
        { src: "housyn.png", href: "/housyn", width: 50 },
        { src: "github.png", href: gitHubLink, width: 50 },
        { src: "linkedin.png", href: "https://linkedin.com/in/ftglass", width: 50 },
        { src: "email.png", href: "mailto:fred@fred.glass", width: 50 },
    ]

    const hexLayouts = {
        0: { length: 10, positions: [2, 1, 3, 4, 0, 5, 6, 7, 8, 9] },
        481: { length: 12, positions: [0, 1, 2, 3, 4, 5, 7, 6, 8, 10] },
        769: { length: 15, positions: [0, 1, 5, 6, 2, 4, 3, 7, 8, 9] },
        1200: { length: 21, positions: [2, 3, 4, 9, 10, 11, 17, 18, 19, 20] },
    }

    const getLayout = (pageWidth) => {
        for (const [width, layout] of Object.entries(hexLayouts).reverse()) {
            if (pageWidth >= width) {
                return layout
            }
        }
    }

    const getItem = (i) => {
        const itemIdx = layout.positions.indexOf(i)
        return items[itemIdx]
    }

    let innerWidth = window.innerWidth;
    let layout = hexLayouts[0]
    $: layout = getLayout(innerWidth)
</script>

<svelte:window
    bind:innerWidth
/>

<div class="grid">
    <ul class="list">
        {#each layout as _, i (i)}
            {@const item = getItem(i)}
            <li class="hex">
                <div class="hex-content">
                    {#if item !== undefined}
                        <div class="hex-outer">
                            <a href={item.href}>
                                <div class="hex-inner">
                                    <img
                                        src={item.src}
                                        style={`width: ${item.width}%;`}
                                        alt="Hex"
                                    />
                                </div>
                            </a>
                        </div>
                    {:else}
                        <div class="hex-outer hex-empty"></div>
                    {/if}
                </div>
            </li>
        {/each}
    </ul>
</div>

<style lang="scss">
    $outline-colour: rgb(52, 58, 64);
    $outer-colour: rgb(40, 43, 46);
    $inner-colour: rgb(52, 58, 64);
    $clip-path: polygon(75% 0, 100% 50%, 75% 100%, 25% 100%, 0 50%, 25% 0);

    @mixin hex-item($amount, $invert) {
        @for $i from 1 through $amount {
            &:nth-of-type(#{$amount}n + #{$i}) {
                grid-column: #{$i + $i - 1} / span 3;
                @if $i % 2 == if($invert, 1, 0) {
                    grid-row: calc(var(--counter) + var(--counter) - 1) / span 2;
                }
            }
        }

        @for $i from 1 through 20 {
            &:nth-of-type(n + #{$i * $amount + 1}) {
                --counter: #{$i + 1};
            }
        }
    }

    .grid {
        width: 100%;
        margin: auto;
        padding: 2.5%;

        .list {
            --amount: 7;
            --counter: 1;
            display: grid;
            list-style-type: none;
            margin: 0;
            padding: 0;
            grid-template-columns: repeat(var(--amount), 1fr 2fr) 1fr;
            grid-gap: 2rem 4rem;
        }

        .hex {
            position: relative;
            grid-column: 1 / span 3;
            grid-row: calc(var(--counter) + var(--counter)) / span 2;
            height: 0;
            padding-bottom: 90%;
        }
    }

    @media screen and (min-width: 1200px) {
        .grid {
            .list {
                --amount: 7;
                --counter: 1;
            }
            .hex {
                @include hex-item(7, false);
            }
        }
    }

    @media screen and (min-width: 769px) and (max-width: 1199px) {
        .grid {
            .list {
                --amount: 5;
                --counter: 1;
            }
            .hex {
                @include hex-item(5, false);
            }
        }
    }

    @media screen and (min-width: 481px) and (max-width: 768px) {
        .grid {
            .list {
                --amount: 3;
                --counter: 1;
            }
            .hex {
                @include hex-item(3, false);
            }
        }
    }

    @media screen and (max-width: 480px) {
        .grid {
            .list {
                --amount: 2;
                --counter: 1;
            }
            .hex {
                @include hex-item(2, true);
            }
        }
    }

    .hex-content {
        position: absolute;
        left: 0;
        top: 0;
        height: 100%;
        width: 100%;
        background-color: $outline-colour;
        clip-path: $clip-path;
        padding: 2px 2px;
    }

    .hex-outer {
        height: 100%;
        width: 100%;
        background-color: $outer-colour;
        clip-path: $clip-path;
        padding: 10px 10px;
        transition: background-color 0.5s ease-in-out;
    }

    .hex-inner {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        width: 100%;
        background-color: $inner-colour;
        clip-path: $clip-path;
        transition: all .3s ease-in-out;
    }

    .hex-inner:hover {
        transform: scale(1.15);
    }

    .hex-empty:hover {
        background-color: $inner-colour;
    }

    img {
      border-radius: 6px;
    }
</style>
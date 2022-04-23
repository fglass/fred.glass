<script>
    const nHexagons = 21
    const gitHubLink = "https://github.com/fglass"
    const hexagons = {
        2: { src: "posergl.png", href: `${gitHubLink}/poser-gl`, width: 60 },
        3: { src: "dragonfire.gif", href: "/dragonfire", width: 80 },
        4: { src: "obsidx.png", href: `${gitHubLink}/obsidx`, width: 45 },
        9: { src: "classes.png", href: "https://classes.gg/", width: 35 },
        10: { src: "portrait.png", href: "/about", width: 100 },
        11: { src: "rpi.png", href: "/rpi", width: 50 },
        17: { src: "housyn.png", href: "/housyn", width: 50 },
        18: { src: "github.png", href: gitHubLink, width: 50 },
        19: { src: "linkedin.png", href: "https://linkedin.com/in/ftglass", width: 50 },
        20: { src: "email.png", href: "mailto:fred@fred.glass", width: 35 },
    }
</script>

<div class="grid">
    <ul class="list">
        {#each {length: nHexagons}  as _, i}
            <li class="hex">
                <div class="hex-content">
                    <div class={`hex-outer ${i in hexagons ? '': 'hex-empty'}`}>
                        {#if i in hexagons}
                            <a href={hexagons[i].href} target={hexagons[i].href.includes('http') ? '_blank': ''}>
                                <div class="hex-inner">
                                    <img
                                        src={hexagons[i].src}
                                        alt="Hex"
                                        style={`width: ${hexagons[i].width}%;`}
                                    />
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
    $outline-colour: rgb(52, 58, 64);
    $outer-colour: rgb(40, 43, 46);
    $inner-colour: rgb(52, 58, 64);
    $clip-path: polygon(75% 0, 100% 50%, 75% 100%, 25% 100%, 0 50%, 25% 0);

    @mixin hex-item($amount) {
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
    }

    .grid {
        width: 100%;
        margin: auto;
        padding: 5%;
        //position: absolute;
        //left: 50%;
        //top: 50%;
        //transform: translate(-50%, -50%);

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

    @media screen and (min-width: 1080px) {
        .grid {
            .list {
                --amount: 7;
                --counter: 1;
            }
            .hex {
                @include hex-item(7);
            }
        }
    }

    @media screen and (min-width: 784px) and (max-width: 1079px) {
        .grid {
            .list {
                --amount: 5;
                --counter: 1;
            }
            .hex {
                @include hex-item(5);
            }
        }
    }

    @media screen and (min-width: 501px) and (max-width: 784px) {
        .grid {
            .list {
                --amount: 3;
                --counter: 1;
            }
            .hex {
                @include hex-item(3);
            }
        }
    }

    @media screen and (max-width: 500px) {
        .grid {
            .list {
                --amount: 2;
                --counter: 1;
            }
            .hex {
                @include hex-item(2);
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
        background-color: rgb(52, 58, 64);
    }
</style>
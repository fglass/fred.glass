<script>
    import { Splide, SplideSlide } from '@splidejs/svelte-splide';
    import '@splidejs/svelte-splide/css';
    export let images;
</script>

<Splide
    aria-label="Media"
    options={{
        type: "loop",
        lazyLoad: true
    }}
>
    {#each images as image}
        <SplideSlide>
            <img src={image.src} alt={image.label} />
        </SplideSlide>
    {/each}
</Splide>


<style>
    img {
        width: 100%;
    }
</style>
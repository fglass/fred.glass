<script>
    export let title = undefined;
    export let image = undefined;
</script>

<svelte:head>
    <title>fred.glass · {title}</title>
</svelte:head>

<div class="container">
    {#if image}
        <div class="mt-4">
            <img src={image} alt="Logo">
        </div>
    {/if}
    <h1 class="title">{title || ''}</h1>
    <div class="content">
        <p class="text">
            <slot />
        </p>
    </div>
</div>

<style>
    .container {
        max-width: 48rem;
    }
    img {
        width: 100%;
        max-width: var(--img-max-width, 500px);
        aspect-ratio: var(--img-aspect-ratio, auto);
    }
    .title {
        font-size: 1.875rem;
        padding-bottom: 15px;
        border-bottom: 1px solid rgba(84, 84, 84, 0.48);
    }
    .content {
        padding-bottom: 15px;
    }
    .text {
        text-align: justify;
        font-size: 16px;
        line-height: 1.5;
    }

    @media screen and (max-width: 480px) {
        .container {
            padding-left: 1rem;
            padding-right: 1rem;
        }
    }
</style>

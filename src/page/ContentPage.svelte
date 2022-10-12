<script>
    export let title;
    export let image;
</script>

<svelte:head>
    <title>fred.glass · {title}</title>
</svelte:head>

<div class="container">
    {#if image}
        <div class="mt-4">
            <img src={image} alt="Image" width="200">
        </div>
    {/if}
    <h1 class="text-light"># {title}</h1>
    <p class="lead text-secondary">
        <slot />
    </p>
</div>

<style>
    .container {
        max-width: 688px;
    }
    h1 {
        padding-bottom: 15px;
        border-bottom: 1px solid rgba(84, 84, 84, 0.48);
    }
    p {
        text-align: justify;
    }
    img {
        margin-bottom: 30px;
        border: 1px solid #343a40;
        border-radius: .25rem;
    }
</style>

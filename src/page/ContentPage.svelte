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
            <img src={image} class={title ? "img-with-title" : ""} alt="Image">
        </div>
    {/if}
    <h1 class="title">{title || ''}</h1>
    <div class="content">
        <p>
            <slot />
        </p>
    </div>
</div>

<style>
    .container {
        max-width: 48rem;
    }
    .title {
        font-size: 1.875rem;
        padding-bottom: 15px;
        border-bottom: 1px solid rgba(84, 84, 84, 0.48);
    }
    .content {
        padding-bottom: 15px;
    }
    .img-with-title {
        margin-bottom: 15px;
        border: 1px solid #343a40;
        border-radius: .25rem;
    }
    p {
        text-align: justify;
        font-size: 16px;
        line-height: 1.5;
    }
</style>

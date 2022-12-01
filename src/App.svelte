<script>
  	import { Router } from "@roxi/routify";
  	import { routes } from "../.routify/routes";
    const imagesToPreload = ["portrait-hex.png"];
</script>

<svelte:head>
    {#each imagesToPreload as image}
      <link rel="preload" as="image" href={image} />
    {/each}
</svelte:head>

<main>
	<Router {routes} />
</main>

<style>
	main {
		text-align: center;
		max-width: none;
		margin: 0 auto;
	}
</style>
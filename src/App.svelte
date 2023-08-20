<script>
  	import { Router } from "@roxi/routify";
  	import { routes } from "../.routify/routes";
</script>

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
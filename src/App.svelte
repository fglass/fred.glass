<script>
	import { Router, Route } from "svelte-routing";
	import Nav from './Nav.svelte';
	import LandingPage from './page/LandingPage.svelte';
	import AboutPage from "./page/AboutPage.svelte";
	import DragonfirePage from "./page/DragonfirePage.svelte";
	import HousynPage from "./page/HousynPage.svelte";
</script>

<main>
	<Router>
		<Nav />
		<Route path="/about"><AboutPage /></Route>
		<Route path="/dragonfire"><DragonfirePage /></Route>
		<Route path="/housyn"><HousynPage /></Route>
		<Route path="/"><LandingPage /></Route>
	</Router>
</main>

<style>
	main {
		text-align: center;
		max-width: none;
		margin: 0 auto;
	}
</style>
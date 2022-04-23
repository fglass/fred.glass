<script>
	import Nav from './Nav.svelte';
	import Hex from './Hex.svelte';
</script>

<main>
	<Nav />
	<Hex />
</main>

<style>
	main {
		text-align: center;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		font-size: 6rem;
		font-weight: bold;
	}

	p {
		font-size: 1.25rem;
	}

	main {
		max-width: none;
	}
</style>
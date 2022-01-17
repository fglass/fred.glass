<script>
	import Nav from './Nav.svelte';
	import Hex from './Hex.svelte';
</script>

<main>
	<Nav />
	<Hex />
	<div class="title">
		<h1>Fred Glass</h1>
		<p>F1 Software Engineer</p>
	</div>
</main>

<style>
	main {
		text-align: center;
		max-width: 240px;
		margin: 0 auto;
	}

	.title {
		position: absolute;
		top: 22%;
		left: 10%;
		color: rgba(255, 255, 255, .55);
		font-family: sans-serif;
		text-align: start;
	}

	h1 {
		font-size: 6rem;
		font-weight: bold;
	}

	p {
		font-size: 1.25rem;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
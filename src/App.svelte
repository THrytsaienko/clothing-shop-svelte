<script lang="ts">
	import Header from "./components/header/Header.svelte";
	import Homepage from "./pages/homepage/Homepage.svelte";
</script>

<main>
	<Header />
	<Homepage />
</main>

<style>
	:global(body) {
		font-family: 'Open Sans Condensed', sans-serif;
		padding: 20px 60px;
	}
	main {
		width: 100%;
	}
	@media screen and (max-width: 800px){
		:global(body) {
			padding: 10px;
		}
	}
</style>
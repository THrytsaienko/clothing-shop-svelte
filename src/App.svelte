<script lang="ts">
	export let name: string;
	import Header from "./components/header/Header.svelte";
</script>

<main>
	<Header />
</main>

<style>
	main {
		text-align: center;
		padding: 20px 60px;
		max-width: 240px;
		margin: 0 auto;
		font-family: 'Open Sans Condensed', sans-serif;
	}

	@media screen and (max-width: 800px){
		main {
			padding: 10px;
		}
	}
</style>
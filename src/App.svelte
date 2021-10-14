<script lang="ts">
	import { Router, Route } from "svelte-navigator";
	import Header from "./components/header/Header.svelte";
	import Homepage from "./pages/homepage/Homepage.svelte";
</script>

<Router>
	<main>
		<Header />
		<Route path="/">
			<Homepage />
		</Route>
		<Route path='/shop'>
			<div>
				<h1>HATS PAGE </h1>
			</div>
		</Route>
		<Route path='/signin'>
			<div>
				<h1>LOGIN PAGE </h1>
			</div>
		</Route>
	</main>
</Router>

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
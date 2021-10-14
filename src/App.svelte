<script lang="ts">
	import { Router, Route } from "svelte-navigator";
	import Header from "./components/header/Header.svelte";
	import HomePage from "./pages/homepage/HomePage.svelte";
	import ShopPage from "./pages/shop/ShopPage.svelte";
</script>

<Router>
	<main>
		<Header />
		<Route path="/">
			<HomePage />
		</Route>
		<Route path='/shop'>
			<ShopPage />
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
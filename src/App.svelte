<script lang="ts">
	import { Router, Route } from "svelte-navigator";
	import { writable } from 'svelte/store';
	import Header from "./components/header/Header.svelte";
	import HomePage from "./pages/homepage/HomePage.svelte";
	import ShopPage from "./pages/shop/ShopPage.svelte";
	import SignInAndSignUpPage from "./pages/sign-in-and-sign-up/SignInAndSignUpPage.svelte";
	import { onMount, onDestroy, setContext } from 'svelte';
	import { auth, createUserProfileDocument } from './firebase/firebase.utils';

	let photos = [];
	let currentUser = writable(null);
	let unsubscribeFromAuth = null;

	onMount(() => {
		unsubscribeFromAuth = auth.onAuthStateChanged(async userAuth => {
			if (userAuth) {
				const userRef = await createUserProfileDocument(userAuth);
				currentUser = userAuth;
				userRef.onSnapshot(snapShot => {
					currentUser = {
						id: snapShot.id,
						...snapShot.data()
					}
				});
			}
		});
	})
	setContext('currentUser', currentUser);

	onDestroy(() => {
		unsubscribeFromAuth();
	})
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
			<SignInAndSignUpPage />
		</Route>
	</main>
</Router>

<style>
	:global(body) {
		font-family: 'Open Sans Condensed', sans-serif;
		padding: 20px 60px;
	}
	:global(*) {
		box-sizing: border-box;
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
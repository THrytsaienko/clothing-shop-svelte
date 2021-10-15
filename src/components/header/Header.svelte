<script lang="ts">
    import { Link } from "svelte-navigator";
    import Logo from "../logo/Logo.svelte";
    import { auth } from '../../firebase/firebase.utils';
    export let currentUser = null;
</script>

<div class="header">
    <div class="logo-container">
        <Link to="/">
            <Logo />
        </Link>
    </div>
    <div class="options">
        <Link class="option" to='/shop'>SHOP</Link>
        <Link class="option" to='/shop'>CONTACT</Link>
        {#if currentUser}
            <div class="option" on:click={() => auth.signOut()}>
                SIGN OUT
            </div>
        {:else}
            <Link class="option" to='/signin'>SIGN IN</Link>
        {/if}
    </div>
</div>

<style>
    .header {
        width: 100%;
        height: 70px;
        margin-bottom: 25px;
        display: flex;
        justify-content: space-between;
    }

    .logo-container {
        height: 100%;
        width: 70px;
        padding: 25px;
    }

    .options {
        width: 50%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: flex-end;
    }

    .options > :global(a) {
        padding: 10px 15px;
        cursor: pointer;
        text-decoration: none;
        color: #000;
    }

    .option {
        padding: 10px 15px;
        cursor: pointer;
    }
</style>
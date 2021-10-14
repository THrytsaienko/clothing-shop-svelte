<script lang="ts">
    import { Link } from "svelte-navigator";
    import Logo from "../logo/Logo.svelte";
</script>

<div class="header">
    <div class="logo">
        <Link to="/">
            <Logo />
        </Link>
    </div>
    <nav>
        <Link class="menu-link" to='/shop'>SHOP</Link>
        <Link class="menu-link" to='/shop'>CONTACT</Link>
        <Link class="menu-link" to='/signin'>SIGN IN</Link>
    </nav>
</div>

<style>
    .header {
        width: 100%;
        height: 70px;
        margin-bottom: 25px;
        display: flex;
        justify-content: space-between;
    }

    .logo > :global(a)  {
        height: 100%;
        width: 70px;
        padding: 25px;
    }

    nav {
        width: 50%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: flex-end;
    }

    nav > :global(a) {
        padding: 10px 15px;
        cursor: pointer;
        text-decoration: none;
        color: #000;
    }
</style>
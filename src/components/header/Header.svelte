<script lang="ts">
    import Logo from "../logo/Logo.svelte";
</script>

<div class="header">
    <a class="logo">
        <Logo />
    </a>
    <nav>
        <a href='/shop'>SHOP</a>
        <a href='/shop'>CONTACT</a>
        <a href='/signin'>SIGN IN</a>
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

    .logo {
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

    a {
        padding: 10px 15px;
        cursor: pointer;
        text-decoration: none;
        color: #000;
    }
</style>
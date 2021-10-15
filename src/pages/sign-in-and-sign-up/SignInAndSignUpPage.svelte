<script>
    import SignIn from "../../components/sign-in/SignIn.svelte";
    import SignUp from "../../components/sign-up/SignUp.svelte";
</script>

<div class='sign-in-and-sign-up'>
    <SignIn />
    <SignUp />
</div>

<style>
    .sign-in-and-sign-up {
        width: 850px;
        display: flex;
        justify-content: space-between;
        margin: 30px auto;
    }
</style>
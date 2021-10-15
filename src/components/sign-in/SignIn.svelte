<script>
    import CustomButton from "../custom-button/CustomButton.svelte";
    import FormInput from "../form-input/FormInput.svelte";
    const handleSubmit = (e) => {
        e.preventDefault();
    }
    const handleChange = (event) => {
        const { value, name } = event.detail;
    }
    let email;
    let password;
</script>

<div class='sign-in'>
    <h2>I already have an account</h2>
    <span>Sign in with your email and password</span>

    <form on:submit={handleSubmit}>
        <FormInput
                name='email'
                type='email'
                on:handleChangeFormInput={handleChange}
                bind:value={email}
                label='email'
                required
        />
        <FormInput
                name='password'
                type='password'
                bind:value={password}
                on:handleChangeFormInput={handleChange}
                label='password'
                required
        />
        <CustomButton type='submit'>Sign in</CustomButton>
    </form>
</div>

<style>
    .sign-in {
        width: 30vw;
        display: flex;
        flex-direction: column;
    }
</style>
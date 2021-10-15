<script>
    import CustomButton from "../custom-button/CustomButton.svelte";
    import FormInput from "../form-input/FormInput.svelte";
    import { signInWithGoogle } from '../../firebase/firebase.utils';
    const handleSubmit = event => {
        event.preventDefault();
        email = '';
        password = '';
    };
    const handleChange = (event) => {
        const { value, name } = event.detail;
        if (name === 'email') {
            email = value;
        }
        if (name === 'password') {
            password = value;
        }
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
        <div class='buttons'>
            <CustomButton type='submit'> Sign in </CustomButton>
            <CustomButton on:click={() => signInWithGoogle} isGoogleSignIn>
                Sign in with Google
            </CustomButton>
        </div>
    </form>
</div>

<style>
    .sign-in {
        width: 30vw;
        width: 380px;
        display: flex;
        flex-direction: column;
    }

    .title {
        margin: 10px 0;
    }

    .buttons {
        display: flex;
        justify-content: space-between;
    }
</style>
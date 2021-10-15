<script>
    import CustomButton from "../custom-button/CustomButton.svelte";
    import FormInput from "../form-input/FormInput.svelte";
    import { auth, createUserProfileDocument } from '../../firebase/firebase.utils';
    let displayName;
    let email;
    let password;
    let confirmPassword;

    const handleChange = event => {
        const { name, value } = event.target;
        if (name === 'displayName') {
            displayName = value;
        }
        if (name === 'email') {
            email = value;
        }
        if (name === 'password') {
            password = value;
        }
        if (name === 'confirmPassword') {
            confirmPassword = value;
        }
    };

    const handleSubmit = async event => {
        event.preventDefault();

        if (password !== confirmPassword) {
            alert("passwords don't match");
            return;
        }

        try {
            const { user } = await auth.createUserWithEmailAndPassword(
                email,
                password
            );

            await createUserProfileDocument(user, { displayName });
            displayName = '';
            email = '';
            password = '';
            confirmPassword = '';
        } catch (error) {
            console.error(error);
        }
    };
</script>

<div class='sign-up'>
    <h2 class='title'>I do not have a account</h2>
    <span>Sign up with your email and password</span>
    <form class='sign-up-form' on:submit={handleSubmit}>
        <FormInput
                type='text'
                name='displayName'
                value={displayName}
                on:change={handleChange}
                label='Display Name'
                required
        />
        <FormInput
                type='email'
                name='email'
                value={email}
                on:change={handleChange}
                label='Email'
                required
        />
        <FormInput
                type='password'
                name='password'
                value={password}
                on:change={handleChange}
                label='Password'
                required
        />
        <FormInput
                type='password'
                name='confirmPassword'
                value={confirmPassword}
                on:change={handleChange}
                label='Confirm Password'
                required
        />
        <CustomButton type='submit'>SIGN UP</CustomButton>
    </form>
</div>

<style>
    .sign-up {
        display: flex;
        flex-direction: column;
        width: 380px;
    }

    .title {
        margin: 10px 0;
    }
</style>
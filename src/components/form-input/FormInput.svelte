<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    export let label;
    export let name;
    export let type = 'text';
    export let required;
    let value = '';
    const handleChange = (e) => {
        value = e.target.value;
        dispatch('handleChangeFormInput', {
            value,
            name: label
        })
    }
</script>

<div class='group'>
    <input {type} {name} {required} {value} class='form-input' on:change={handleChange} />
    {#if label}
        <label class={`${value.length ? 'shrink' : ''} form-input-label`}>
            {label}
        </label>
    {/if}
</div>

<style>
    :root {
        --sub-color: grey;
        --main-color: black;
    }
    .group {
        position: relative;
        margin: 45px 0;
    }

    .form-input {
        background: none;
        background-color: white;
        color: var(--sub-color);
        font-size: 18px;
        padding: 10px 10px 10px 5px;
        display: block;
        width: 100%;
        border: none;
        border-radius: 0;
        border-bottom: 1px solid var(--sub-color);
        margin: 25px 0;
    }

    .form-input:focus {
         outline: none;
     }

    .form-input:focus ~ .form-input-label {
        top: -14px;
        font-size: 12px;
        color: var(--main-color);
     }

    input[type='password'] {
        letter-spacing: 0.3em;
    }

    .form-input-label {
        color: var(--sub-color);
        font-size: 16px;
        font-weight: normal;
        position: absolute;
        pointer-events: none;
        left: 5px;
        top: 10px;
        transition: 300ms ease all;
    }

    .form-input-label.shrink {
        top: -14px;
        font-size: 12px;
        color: var(--main-color);
     }
</style>
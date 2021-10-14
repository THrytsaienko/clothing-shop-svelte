<script>
    import Directory from "../../components/directory/Directory.svelte";
</script>

<div class='homepage'>
    <Directory />
</div>

<style>
    .homepage {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px 80px;
    }
    @media screen and (max-width: 800px){
        .homepage {
            padding: 10px;
        }
    }
</style>
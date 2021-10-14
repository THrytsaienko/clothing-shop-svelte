<script lang="ts">
    import MenuItem from "../menu-item/MenuItem.svelte";
    type section = {
        title: string,
        imageUrl: string,
        id: number
    }
    const sections: section[] = [
        {
            title: 'hats',
            imageUrl: 'https://i.ibb.co/cvpntL1/hats.png',
            id: 1
        },
        {
            title: 'jackets',
            imageUrl: 'https://i.ibb.co/px2tCc3/jackets.png',
            id: 2
        },
        {
            title: 'sneakers',
            imageUrl: 'https://i.ibb.co/0jqHpnp/sneakers.png',
            id: 3
        },
        {
            title: 'womens',
            imageUrl: 'https://i.ibb.co/GCCdy8t/womens.png',
            size: 'large',
            id: 4
        },
        {
            title: 'mens',
            imageUrl: 'https://i.ibb.co/R70vBrQ/men.png',
            size: 'large',
            id: 5
        }
    ]
</script>

<div class='directory-menu'>
    {#each sections as {id, title, imageUrl, size} (id)}
        <MenuItem title={title} imageUrl={imageUrl} size={size} />
    {/each}
</div>

<style>
    .directory-menu {
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
</style>
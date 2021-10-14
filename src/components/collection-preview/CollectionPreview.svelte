<script lang="ts">
    import CollectionItem from "../collection-item/CollectionItem.svelte";
    type Item = {
        id: number,
        name: string,
        imageUrl: string,
        price: number
    }
    export let title: string;
    export let items: Item[]
</script>

<div class='collection-preview'>
    <h1 class='title'>{title.toUpperCase()}</h1>
    <div class='preview'>
        {#each items as item, idx (item.id)}
            {#if idx < 4}
                <CollectionItem {...item} />
            {/if}
        {/each}
    </div>
</div>

<style>
    .collection-preview {
        display: flex;
        flex-direction: column;
        margin-bottom: 30px;
    }

    .title {
        font-size: 28px;
        margin-bottom: 25px;
    }

    .preview {
        display: flex;
        justify-content: space-between;
    }
</style>
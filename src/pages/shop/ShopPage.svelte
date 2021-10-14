<script lang="ts">
    import SHOP_DATA from "./data";
    import CollectionPreview from "../../components/collection-preview/CollectionPreview.svelte";

    type Item = {
        id: number,
        name: string,
        imageUrl: string,
        price: number
    }

    type Section = {
        id: number,
        title: string,
        routeName: string,
        items: Item[]
    }
    let collections: Section[] = SHOP_DATA;
</script>

<div class='shop-page'>
    {#each collections as collection (collection.id)}
        <CollectionPreview title={collection.title} items={collection.items} />
    {/each}
</div>
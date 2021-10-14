<script lang="ts">
    export let imageUrl: string;
    export let name: string;
    export let price: number;
</script>

<div class='collection-item'>
    <div class='image' style="background-image: url('{imageUrl}')"/>
    <div class='collection-footer'>
        <span class='name'>{name}</span>
        <span class='price'>{price}</span>
    </div>
</div>

<style>
    .collection-item {
        width: 22%;
        display: flex;
        flex-direction: column;
        height: 350px;
        align-items: center;
    }

    .collection-item .image {
        width: 100%;
        height: 95%;
        background-size: cover;
        background-position: center;
        margin-bottom: 5px;
    }

    .collection-footer {
        width: 100%;
        height: 5%;
        display: flex;
        justify-content: space-between;
        font-size: 18px;
    }

    .collection-footer .name {
        width: 90%;
        margin-bottom: 15px;
    }

    .price {
        width: 10%;
    }
</style>
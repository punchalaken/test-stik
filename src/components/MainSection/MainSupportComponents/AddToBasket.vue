<template>
    <div class="main_basket">
        <div class="add-button">ДОБАВИТЬ В КОРЗИНУ</div>
        <div class="add-bookmarks">
            <img src="images/SVG/bookmarks.svg" alt="Добавить в закладки" />
        </div>
    </div>
</template>

<script>
export default {
    components: {},
    name: 'AddToBasket'
}
</script>

<style scoped lang="scss">
.main_basket {
    display: flex;
    gap: 10px;

    margin-top: 36px;

    .add-button {
        width: 306px;
        height: 44px;

        display: flex;
        align-items: center;
        justify-content: center;

        background-color: black;
        color: white;

        cursor: pointer;
    }

    .add-bookmarks {
        width: 44px;
        height: 44px;
        border: 1px solid black;

        display: flex;
        align-items: center;
        justify-content: center;

        cursor: pointer;
    }
}
</style>

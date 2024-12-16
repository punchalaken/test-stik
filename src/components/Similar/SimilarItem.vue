<template>
    <a class="similar__item" href="#">
        <img class="similar__img" :src="path" alt="Фото платья" />
        <div class="similar__item-container">
            <span>{{ title }}</span>
            <div class="similar__price">
                <div class="new-price">{{ price }}</div>
                <div class="old-price">{{ oldPrice }}</div>
            </div>
        </div>
    </a>
</template>

<script>
export default {
    components: {},
    name: 'SimilarItem',
    props: {
        path: {
            type: String,
            required: true
        },
        title: {
            type: String,
            required: true
        },
        price: {
            type: String,
            required: true
        },
        oldPrice: {
            type: Number,
            required: false,
            default: null
        }
    }
}
</script>

<style scoped lang="scss">
.similar__item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px;

    .similar__img {
        width: 100%;
        max-width: 333px;
        height: auto;
    }

    .similar__item-container {
        max-width: 279px;
        height: 38px;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 10px;

        font-size: 10px;
        color: #333333;

        .similar__price {
            display: flex;
            gap: 10px;

            .old-price {
                color: #828282;
                text-decoration: line-through;
            }
        }
    }
}
</style>

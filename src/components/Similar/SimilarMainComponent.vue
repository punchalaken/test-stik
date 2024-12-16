<template>
    <a class="similar">
        <h3 class="similar__title">Похожие товары</h3>
        <div class="similar__items">
            <SimilarItem
                v-for="item in simiralObject"
                :key="item.id"
                :path="item.path"
                :title="item.title"
                :price="item.price"
                :old-price="item.oldPrice"
            />
        </div>
    </a>
</template>

<script>
import SimilarItem from './SimilarItem.vue'

export default {
    components: {
        SimilarItem
    },
    name: 'SimilarMainComponent',
    data() {
        return {
            simiralObject: [
                {
                    id: 0,
                    path: 'images/SimilarImages/image-1.png',
                    title: 'ПЛАТЬЕ С V-ОБРАЗНЫМ ВЫРЕЗОМ, БЕЛЫЙ',
                    price: '14 900 RUB',
                    oldPrice: '8 000 RUB'
                },
                {
                    id: 1,
                    path: 'images/SimilarImages/image-2.png',
                    title: 'ЖАКЕТ ДВУБОРТНЫЙ, СЕРО-ГОЛУБОЙ',
                    price: '8900 RUB'
                },
                {
                    id: 2,
                    path: 'images/SimilarImages/image-3.png',
                    title: 'ПЛАТЬЕ МАКСИ С ЯРУСАМИ, БЕЛЫЙ',
                    price: '10 500 RUB'
                },
                {
                    id: 3,
                    path: 'images/SimilarImages/image-4.png',
                    title: 'КОМБИНЕЗОН СО СТОЙКОЙ, ЧёРНЫЙ',
                    price: '9500 RUB'
                }
            ]
        }
    }
}
</script>

<style scoped lang="scss">
.similar {
    width: 100%;
    max-width: 1360px;
    margin-top: 42px;

    display: flex;
    flex-direction: column;
    gap: 31px;

    @media screen and (max-width: 700px) {
        padding-inline: 16px;
    }

    .similar__title {
        text-transform: uppercase;
        font-size: 12px;

        font-weight: 400;
    }

    .similar__items {
        width: 100%;
        display: grid;
        gap: 8px;
        row-gap: 32px;
        grid-template-columns: repeat(4, 1fr);

        @media screen and (max-width: 1300px) {
            grid-template-columns: repeat(2, 1fr);
        }
    }
}
</style>

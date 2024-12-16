<template>
    <div class="main__description">
        <span class="main__description-header">{{ name }}</span>
        <span class="main__description-price">{{ price }}</span>
        <div class="main__descriptino-sizes">
            <span class="main-title">Размеры</span>
            <div class="sizes">
                <SizesComponent
                    v-for="item in sizeObj"
                    :key="item.id"
                    :title="item.title"
                    :value="item.value"
                />
            </div>
        </div>
        <div class="main__description-color">
            <div class="color-title">Цвет</div>
            <div class="color-container">
                <SearchColor
                    v-for="item in colorObj"
                    :key="item.id"
                    :path="item.path"
                    :alt="item.alt"
                    :selected="selectedItem === item.id"
                    @select="handleSelect(item.id)"
                />
            </div>
        </div>
        <AddToBasket />
        <SomeCharacters />
    </div>
</template>

<script>
import AddToBasket from './AddToBasket.vue'
import SearchColor from './SearchColor.vue'
import SizesComponent from './SizesComponent.vue'
import SomeCharacters from './SomeCharacters.vue'

export default {
    components: {
        SizesComponent,
        SearchColor,
        AddToBasket,
        SomeCharacters
    },
    name: 'DescriptionItem',
    data() {
        return {
            name: 'Жакет удлиненный, белый',
            price: '8900 rub',
            selectedItem: 0,
            sizeObj: [
                { id: 0, title: 'XS', value: 2 },
                { id: 1, title: 'S', value: 200 },
                { id: 2, title: 'M', value: 0 }
            ],
            colorObj: [
                { id: 0, path: 'images/color-svg/white.svg', alt: 'Белый' },
                { id: 1, path: 'images/color-svg/black.svg', alt: 'Черный' },
                { id: 2, path: 'images/color-svg/beige.svg', alt: 'Бежевый' }
            ]
        }
    },
    methods: {
        handleSelect(id) {
            this.selectedItem = this.selectedItem === id ? null : id
        }
    }
}
</script>

<style scoped lang="scss">
.main__description {
    display: flex;
    flex-direction: column;

    margin-left: 31px;

    @media screen and (max-width: 700px) {
        margin-left: 0;
    }

    .main__description-header {
        text-transform: uppercase;
        height: 16px;
    }
    .main__description-price {
        text-transform: uppercase;
        margin-top: 0.5rem;
        height: 16px;
    }

    .main__descriptino-sizes {
        display: flex;
        flex-direction: column;

        margin-top: 31px;

        .sizes-title {
            color: #4f4f4f;
        }

        .sizes {
            display: flex;
            gap: 14px;

            margin-top: 8px;
        }
    }

    .main__description-color {
        margin-top: 36px;
        font-size: 10px;

        .color-container {
            display: flex;
            gap: 16px;

            margin-top: 8px;
        }
    }
}
</style>

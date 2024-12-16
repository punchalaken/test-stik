<template>
    <nav class="header__menu">
        <ul class="header__items">
            <NavListItem
                v-for="item in imageObject"
                :key="item.id"
                :image="item.path"
                :alt="item.alt"
            />
        </ul>
    </nav>
</template>

<script>
import NavListItem from './NavListItem.vue'

export default {
    components: {
        NavListItem
    },
    name: 'NavPonel',
    data() {
        return {
            imageObject: [
                {
                    id: 0,
                    path: 'images/SVG/search.svg',
                    alt: 'Поиск'
                },
                {
                    id: 1,
                    path: 'images/SVG/bookmarks.svg',
                    alt: 'Закладки'
                },
                {
                    id: 2,
                    path: 'images/SVG/profile.svg',
                    alt: 'Профиль'
                },
                {
                    id: 3,
                    path: 'images/SVG/basket.svg',
                    alt: 'Корзина'
                }
            ]
        }
    }
}
</script>

<style scoped lang="scss">
.header__items {
    display: flex;
    gap: 1rem;
}
</style>

<template>
    <main class="main">
        <div class="main__left-ponel">
            <LeftImgItem
                v-for="item in imageLeftObj"
                :key="item.id"
                :path="item.path"
                :alt="item.alt"
                :selected="selectedItem === item.id"
                @select="handleSelect(item.id)"
            />
        </div>
        <MainPhotoComponent
            :selected="selectedItem"
            :totalItems="imageLeftObj.length"
            @update:selected="updateSelectedItem"
        />
        <DescriptionItem />
    </main>
</template>

<script>
import DescriptionItem from './MainSupportComponents/DescriptionItem.vue'
import LeftImgItem from './MainSupportComponents/LeftImgItem.vue'
import MainPhotoComponent from './MainSupportComponents/MainPhotoComponent.vue'

export default {
    components: {
        LeftImgItem,
        MainPhotoComponent,
        DescriptionItem
    },
    name: 'MainSectionComponent',
    data() {
        return {
            selectedItem: 0,
            imageLeftObj: [
                { id: 0, path: 'images/left-ponel/image-left-1.png', alt: 'Пример номер 1' },
                { id: 1, path: 'images/left-ponel/image-left-2.png', alt: 'Пример номер 2' },
                { id: 2, path: 'images/left-ponel/image-left-3.png', alt: 'Пример номер 3' }
            ]
        }
    },
    methods: {
        handleSelect(id) {
            this.selectedItem = this.selectedItem === id ? null : id
        },
        updateSelectedItem(newSelectedItem) {
            this.selectedItem = newSelectedItem
        }
    }
}
</script>

<style scoped lang="scss">
.main {
    display: flex;
    justify-content: center;
    gap: 30px;

    @media screen and (max-width: 950px) {
        flex-wrap: wrap;
    }

    .main__left-ponel {
        display: flex;
        flex-direction: column;
        gap: 0.25rem;

        @media screen and (max-width: 1050px) {
            display: none;
        }
    }
}
</style>

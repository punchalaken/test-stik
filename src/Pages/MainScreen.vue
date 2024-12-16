<template>
    <div class="wrapper">
        <component :is="currentHeader" />
        <MainSectionComponent />
        <SimilarMainComponent />
    </div>
</template>

<script>
import HeaderMobile from '@/components/Header/HeaderMobile.vue'
import MainHeaderComponent from '@/components/Header/MainHeaderComponent.vue'
import MainSectionComponent from '@/components/MainSection/MainSectionComponent.vue'
import SimilarMainComponent from '@/components/Similar/SimilarMainComponent.vue'

export default {
    components: {
        MainHeaderComponent,
        HeaderMobile,
        MainSectionComponent,
        SimilarMainComponent
    },
    data() {
        return {
            isMobile: window.innerWidth <= 700
        }
    },
    computed: {
        currentHeader() {
            return this.isMobile ? 'HeaderMobile' : 'MainHeaderComponent'
        }
    },
    mounted() {
        window.addEventListener('resize', this.handleResize)
    },
    beforeDestroy() {
        window.removeEventListener('resize', this.handleResize)
    },
    methods: {
        handleResize() {
            this.isMobile = window.innerWidth <= 700
        }
    },
    name: 'MainScreen'
}
</script>

<style>
.wrapper {
    width: 100%;

    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>

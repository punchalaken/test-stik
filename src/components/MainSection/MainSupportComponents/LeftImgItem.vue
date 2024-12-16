<template>
    <div class="image-container" @click="toggleSelection">
        <img class="main__left-ponel__img" :src="path" :alt="alt" />
        <div v-if="selected" class="overlay"></div>
    </div>
</template>

<script>
export default {
    name: 'LeftImgItem',
    props: ['path', 'alt', 'selected'],
    methods: {
        toggleSelection() {
            this.$emit('select', this.selected ? null : this.id)
        }
    }
}
</script>

<style scoped lang="scss">
.image-container {
    position: relative;
    display: inline-block;

    cursor: pointer;

    .main__left-ponel__img {
        width: 70px;
        height: 88px;
        transition:
            filter 0.3s ease,
            opacity 0.3s ease;
    }

    .overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgba(255, 255, 255, 0.5);
        pointer-events: none;
    }
}
</style>

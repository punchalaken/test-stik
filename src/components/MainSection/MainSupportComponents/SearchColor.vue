<template>
    <div @click="toggleSelection" class="color-wrapper">
        <img class="color-img" :src="path" :alt="`${alt} цвет`" />
        <div v-if="selected" class="underline"></div>
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
.color-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    gap: 3px;

    width: 34px;
    height: 31px;

    .color-img {
        cursor: pointer;
        width: 27px;
        height: 27px;
    }

    .underline {
        background-color: #4f4f4f;
        width: 34px;
        height: 1px;
    }
}
</style>

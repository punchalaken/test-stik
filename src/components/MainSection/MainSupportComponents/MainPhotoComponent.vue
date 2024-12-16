<template>
    <div class="photo-wrapper">
        <img
            class="main__photo"
            :src="`images/MainImage/image-${selected}.png`"
            :alt="`Фото номер ${selected}`"
        />
        <div class="main__photo-arrow-togle">
            <img
                :class="{ disableBack: disableBack }"
                src="images/SVG/arrowLeft.svg"
                alt="Предыдущая картинка"
                @click="toggleBack"
                :disabled="disableBack"
            />
            <img
                :class="{ disableForvard: disableForvard }"
                src="images/SVG/arrowRight.svg"
                alt="Следующая картинка"
                @click="toggleForward"
                :disabled="disableForvard"
            />
        </div>
    </div>
</template>

<script>
export default {
    name: 'MainPhotoComponent',
    props: ['selected', 'totalItems'],
    computed: {
        disableBack() {
            return this.selected === 0
        },
        disableForvard() {
            return this.selected === this.totalItems - 1
        }
    },
    methods: {
        toggleForward() {
            if (this.selected < this.totalItems - 1) {
                this.$emit('update:selected', this.selected + 1)
            }
        },
        toggleBack() {
            if (this.selected > 0) {
                this.$emit('update:selected', this.selected - 1)
            }
        }
    }
}
</script>

<style scoped lang="scss">
.photo-wrapper {
    position: relative;

    .main__photo {
        max-width: 518px;
        width: 100%;
    }

    .main__photo-arrow-togle {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        width: 100%;
        padding-inline: 1rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        cursor: pointer;
    }

    .disableBack,
    .disableForvard {
        opacity: 0.5;
        pointer-events: none;
    }
}
</style>

<template>
    <div>
        <div class="character">
            <span class="character__title">Описание</span
            ><img src="images/SVG/plus.svg" alt="Подробнее" />
        </div>
        <div class="character">
            <span class="character__title">Состав и уход</span
            ><img src="images/SVG/plus.svg" alt="Подробнее" />
        </div>
    </div>
</template>

<script>
export default {
    components: {},
    name: 'SomeCharacters'
}
</script>

<style scoped lang="scss">
.character {
    display: flex;
    justify-content: space-between;
    align-items: center;
    widows: 360px;
    height: 41px;

    padding-right: 7px;

    border-bottom: 1px solid #e0e0e0;

    font-size: 10px;

    cursor: pointer;

    &:first-child {
        margin-top: 40px;

        border-top: 1px solid #e0e0e0;
    }

    .character__title {
        text-transform: uppercase;
    }
}
</style>

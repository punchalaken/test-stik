<template>
    <div class="size-wrapper">
        <div class="size-item" :class="{ zero: value === 0 }">{{ title }}</div>
        <div v-if="value === 0" class="zero">подписка</div>
        <div v-else-if="value < 5" class="few">мало</div>
    </div>
</template>

<script>
export default {
    name: 'SizesComponent',
    props: ['title', 'value']
}
</script>

<style scoped lang="scss">
.size-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 3px;

    .size-item {
        width: 65px;
        height: 31px;

        display: flex;
        align-items: center;
        justify-content: center;

        border: 1px solid #333333;

        font-size: 10px;

        cursor: pointer;
    }

    .few {
        color: #828282;
    }

    .zero {
        color: #bdbdbd;
        border-color: #bdbdbd;

        cursor: default;
    }
}
</style>

<template>
    <header class="header">
        <a class="header__logo" href="#">
            <img src="/images/logo.png" alt="Магазин STIK" />
        </a>
        <NavPonel />
    </header>
</template>

<script>
import NavPonel from './HeaderSupportComponents/NavPonel.vue'

export default {
    components: {
        NavPonel
    },
    name: 'MainHeaderComponent'
}
</script>

<style scoped lang="scss">
.header {
    width: 100%;
    max-width: 1440px;
    height: 86px;

    display: flex;
    justify-content: flex-end;
    align-items: center;

    position: relative;

    .header__logo {
        position: absolute;
        left: 50%;
        transform: translate(-50%);

        img {
            width: 54px;
            height: 28px;
        }
    }
}
</style>

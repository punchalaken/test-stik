<template>
    <header class="header">
        <nav class="header__nav">
            <ul class="header__list">
                <div class="header__wrapper-items">
                    <li class="header__item"><img src="images/SVG/profile.svg" alt="Профиль" /></li>
                    <li class="header__item"><img src="images/SVG/search.svg" alt="Поиск" /></li>
                </div>
                <li class="header__item"><img src="images/SVG/basket.svg" alt="Корзина" /></li>
            </ul>
        </nav>
        <a class="header__logo" href="#">
            <img src="/images/logo.png" alt="Магазин STIK" />
        </a>
    </header>
</template>

<script>
export default {
    components: {},
    name: 'MainHeaderComponent'
}
</script>

<style scoped lang="scss">
.header {
    width: 100%;
    max-width: 700px;
    height: 50px;

    display: flex;
    align-items: center;

    position: relative;

    .header__nav {
        width: 100%;
        padding: 16px;

        .header__list {
            width: 100%;

            display: flex;
            justify-content: space-between;

            .header__wrapper-items {
                display: flex;
                gap: 16px;

                .header__item {
                    cursor: pointer;
                }
            }
        }
    }

    .header__logo {
        position: absolute;
        left: 50%;
        transform: translate(-50%);

        img {
            width: 38px;
            height: 17px;
        }
    }
}
</style>

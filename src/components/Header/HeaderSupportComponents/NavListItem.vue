<template>
    <li class="header__item">
        <a href="#" class="header__link">
            <img :src="image" :alt="alt" />
        </a>
    </li>
</template>

<script>
export default {
    name: 'NavListItem',
    props: ['image', 'alt']
}
</script>

<style scoped lang="scss"></style>

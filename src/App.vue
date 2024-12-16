<template>
    <div id="app">
        <MainScreen />
    </div>
</template>

<script>
import MainScreen from './Pages/MainScreen.vue'
import './assets/styles/normalize.css'
import './assets/styles/fonts.css'

export default {
    name: 'App',
    components: {
        MainScreen
    }
}
</script>

<style>
#app {
    font-family: 'Helvetica';

    width: 100%;
    font-size: 12px;
    color: #333333;

    margin-bottom: 40px;
}
</style>

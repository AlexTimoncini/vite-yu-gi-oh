<script>
import MainOptions from './MainOptions.vue';
    import MainCardGrid from './MainCardGrid.vue';
    export default{
        name: 'MainApp',
        components: {
            MainCardGrid,
            MainOptions
        }
    }
</script>

<template>
    <main>
        <MainOptions />
        <MainCardGrid />
    </main>
</template>

<style lang="scss" scoped>
    main{
        padding: 3rem 1rem;
    }
</style>

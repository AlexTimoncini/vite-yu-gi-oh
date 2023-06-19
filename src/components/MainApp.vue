<script>
    import MainCardGrid from './MainCardGrid.vue';
    export default{
        name: 'MainApp',
        components: {
            MainCardGrid,
        }
    }
</script>

<template>
    <main>
        <MainCardGrid />
    </main>
</template>

<style lang="scss" scoped>
    main{
        padding: 3rem 1rem;
    }
</style>

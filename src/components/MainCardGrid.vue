<script>
    import LoaderApp from './LoaderApp.vue';
    import MainCard from './MainCard.vue';
    export default{
        name: 'MainCardGrid',
        components: {
            MainCard,
            LoaderApp,
        },
        data(){
            return{
            }
        },
        props: {
            cardGrid : Array,
        }
    }
</script>

<template>
    <LoaderApp v-if="cardGrid.length === 0" />
    <div class="ivy_container" v-else>
        <div class="ivy_counter">
            Found {{ cardGrid.length }} cards
        </div>
        <ul>
            <MainCard v-for="card in cardGrid" :img="card.card_images[0].image_url" />
        </ul>
    </div>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixin.scss' as *;
    @use '../styles/partials/variables.scss' as *;
    .ivy_counter{
        background-color: rgb(238, 220, 133);
        padding: 1rem 3rem;
        font-family: sans-serif;
        font-size: 1.5rem;
        margin-top: 2rem;
        border-top-right-radius: 1rem;
        border-top-left-radius: 1rem;
    }
    ul{
        @include flex(row, center, center, wrap);
        background-color: $secBg;
        gap: 2rem;
        padding: 2rem;
        border-bottom-right-radius: 1rem;
        border-bottom-left-radius: 1rem;
        list-style: none;
        width: 100%;
    }
</style>

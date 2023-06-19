<script>
    import MainOptions from './MainOptions.vue';
    import LoaderApp from './LoaderApp.vue';
    import MainCard from './MainCard.vue';
    import axios from 'axios';
    import { store } from '../store.js';
    export default{
        name: 'MainCardGrid',
        components: {
            MainCard,
            LoaderApp,
            MainOptions,
        },
        data(){
            return{
                cardList: [],
            }
        },
        created(){
            axios.get(store.apiUrl).then( (response) => {
                this.cardList = response.data.data;
                console.log(this.cardList);
            })
            .catch(function (error){
                console.log(error);
            });
        }
    }
</script>

<template>
    <MainOptions />
    <LoaderApp v-if="cardList.length === 0" />
    <div class="ivy_container" v-else>
        <div class="ivy_counter">
            Found {{ cardList.length }} cards
        </div>
        <ul>
            <MainCard v-for="card in cardList" :img="card.card_images[0].image_url" />
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
        border-radius: 1rem;
    }
    ul{
        @include flex(row, center, center, wrap);
        background-color: $secBg;
        gap: 2rem;
        padding: 2rem;
        border-radius: 1rem;
        list-style: none;
        width: 100%;
    }
</style>

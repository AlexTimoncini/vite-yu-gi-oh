<script>
    import MainCard from './MainCard.vue';
    import axios from 'axios';
    export default{
        name: 'MainCardGrid',
        components: {
            MainCard,
        },
        data(){
            return{
                cardList: [],
            }
        },
        created(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Lyrilusc').then( (response) => {
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
    <ul>
        <MainCard v-for="card in cardList" :img="card.card_images[0].image_url" />
    </ul>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixin.scss' as *;
    @use '../styles/partials/variables.scss' as *;
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

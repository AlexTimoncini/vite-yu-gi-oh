<script>
    import MainOptions from './MainOptions.vue';
    import axios from 'axios';
    import MainCardGrid from './MainCardGrid.vue';
    export default{
        name: 'MainApp',
        components: {
            MainCardGrid,
            MainOptions,
        },
        data(){
            return{
                cardList: [],
            }
        },
        methods: {
                callApi(url){
                    axios.get(url).then( (response) => {
                    this.cardList = response.data.data;
                    console.log(this.cardList);
                })
                .catch(function (error){
                    console.log(url);
                });
                }
            },
            created(){
                this.callApi('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Lyrilusc')
            }
    }
</script>

<template>
    <main>
        <MainOptions @cardFilter="callApi"/>
        <MainCardGrid :cardGrid="cardList"/>
    </main>
</template>

<style lang="scss" scoped>
    main{
        padding: 3rem 1rem;
    }
</style>

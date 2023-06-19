<script>
    import axios from 'axios';
    export default{
        name: 'MainCardGrid',
        data(){
            return{
                cardList: [],
            }
        },
        created(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Lyrilusc').then( (response) => {
                this.cardList = response.data.data;
                console.log(this.cardList)
            })
            .catch(function (error){
                console.log(error);
            });
        }
    }
</script>

<template>
    <h1>{{ cardList[1].id }}</h1>
</template>

<style lang="scss" scoped>
    
</style>

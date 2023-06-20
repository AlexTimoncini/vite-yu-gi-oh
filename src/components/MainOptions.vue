<script>
    import axios from 'axios';
    export default{
        name: 'MainOptions',
        data(){
            return{
                arcList: [],
            }
        },
        methods: {
            getUrl(parameter){
                let generalUrl = 'https://db.ygoprodeck.com/api/v7/cardinfo.php';
                return `${generalUrl}?archetype=${parameter}`; 
            }
        },
        created(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then( (response) => {
                this.arcList = response.data;
                console.log(this.arcList)
            })
            .catch (function (error){
                console.log(error)
            });
        }
    }
</script>

<template>
    <div class="ivy_container">
        <select name="arcList" id="arcList">
            <option value="" selected disabled>Choose your archetype</option>
            <option v-for="arc in arcList" value="arc.archetype_name" @click="$emit('CardFilter', getUrl(arc.archetype_name))">{{ arc.archetype_name }}</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
    
</style>

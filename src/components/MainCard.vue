<script>
    export default{
        name: 'MainCard',
        props: {
            img : String,
        }
    }

</script>

<template>
    <li>
        <img :src="img" alt="">
    </li>
</template>

<style lang="scss" scoped>
    li{
        width: 300px;

        img{
            width: 100%;
        }

        
    }
</style>

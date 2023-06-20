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
        <div class="card">
            <img :src="img" alt="" loading="lazy" class="front">
            <img src="../assets/card_back.png" alt="yugioh card back" class="back">
        </div>
    </li>
</template>

<style lang="scss" scoped>
    li{
        width: 300px;
        position: relative;
        height: 440px;
        cursor: pointer;
        .card{
            transition: all 0.33s linear;
            transform-style: preserve-3d;
            box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.3);

            img{
                width: 100%;
                position: absolute;
            }
    
            .front{
                z-index: 2;
                backface-visibility: hidden;
            }
    
            .back{
                z-index: 1;
                transform: rotateY(180deg);
            }
        }
        &:hover .card{
            transform: rotateY(180deg);
        }

    }
</style>

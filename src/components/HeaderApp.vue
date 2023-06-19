<script>
    export default{
        name: 'HeaderApp'
    }
</script>

<template>
    <header>
        <nav>
            <div class="ivy_logo_box">
                <img src="../assets/Yu-Gi-Oh_logo.webp" alt="Yugioh logo" class="ivy_logo" draggable="false">
            </div>
            <h1>Yu-Gi-Oh > Magic</h1>
        </nav>
    </header>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables.scss' as *;
    nav{
        background-color: $secBg;
        padding: 0.5rem 2rem;
        display: flex;
        align-items: center;
        .ivy_logo_box{
            height: 100px;

            img{
                height: 100%;
            }
        }
        h1{
            font-size: 3rem;
            font-family: sans-serif;
            margin-left: 3rem;
        }
    }
</style>

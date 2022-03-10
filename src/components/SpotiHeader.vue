<template>
    <header>
        <div class="container">
            <img src="../assets/spotyLogo.png" alt="">
        </div>
    </header>
</template>

<script>
export default {
    name: 'SpotiHeader'
}
</script>

<style lang="scss">
    header{
        width: 100%;
        height: 10vh;
        background-color: #2E3A46;
        display: flex;
        align-items: center;
        .container{
            width: 80px;
            height: 80px;
            // border: 1px solid red;
            margin-left: 20px;
            img{
                width: 100%;
                height: 100%;
                object-fit: cover;
                background-color: #2E3A46;
                border-radius: 9999px;
            };
        };
    };
</style>
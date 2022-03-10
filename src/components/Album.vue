<template>
    <div class="album">
        <img :src="OneAlbum.poster">
        <h5>{{OneAlbum.title}}</h5>
        <span>{{OneAlbum.author}}</span>
        <span>{{OneAlbum.year}}</span>
    </div>  
</template>

<script>
export default {
    name: 'OneAlbum',
    props:{
        OneAlbum:{
            type: Object,
            required: true,
        }
    }
}
</script>

<style lang="scss">
    .album{
        width: 18%;
        height: 350px;
        background-color: #2E3A46;
        display: flex;
        flex-direction: column;
        align-items: center;

        img{
            width: 150px;
            height: 150px;
            padding: 10px 0px;
        }
        h5{
            text-transform: uppercase;
            color: white;
            font-size: 22px;
            padding: 5px 5px;
        }
        span{
            color: silver;
            font-size: 16px;
            padding: 2px 0px;
        }
    }
</style>
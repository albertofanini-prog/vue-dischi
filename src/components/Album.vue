<template>
    <div class="album">
        <img :src="OneAlbum.poster">
        <h5>{{OneAlbum.title}}</h5>
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
<template>
    <section>
        <div class="container">
            <!-- <div v-if="isLoading" class="loading"></div> -->

            <div v-cloak class="album_wrapper">
                <OneAlbum v-for="(album, index) in albums" :key="index" :OneAlbum="album"/>
            </div>
        </div>
    </section>
</template>

<script>
import OneAlbum from './Album.vue'
import axios from 'axios'

export default {
    name: 'AlbumList',
    components:{
        OneAlbum,
    },
    data() {
        return {
            albums:[],
            isLoading: true,
        }
    },
    methods:{
        //Creare funzione per utilizzare i dati più volte richiamandola
        getAlbums: function(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then( res => {
                console.log(res.data.response); //res.data = dati ricevuti dal server
                this.albums = res.data.response; //array di dati = dati ricevuti dal server
                
            })
            .finally( () => (this.isLoading = false))
            //Ricevere errori dal server:
            // .catch( err => {
            //     console.warn(err.response);
            // })
        },
    },
    created(){
        //Fornire i dati 
        this.getAlbums()
    }
}
</script>

<style lang="scss" scoped>
section{
    height: 100%;
    // border: 2px solid yellow;
    display: flex;
    align-items: center;
} .container{
        height: 100%;
    }
    .album_wrapper{
        height: 100%;
        display: flex;
        flex-wrap: wrap;
        gap: 15px 20px;
        padding: 1% 20%;
        // border: 1px solid red;
        .loading {
        background-color: red;
        height: 400px;
        width: 400px;
        }
    }
</style>
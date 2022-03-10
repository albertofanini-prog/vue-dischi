<template>
    <section>
        <div class="container">
            <div class="album_wrapper">
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
            //Ricevere errori dal server:
            // .catch( err => {
            //     console.warn(err.response);
            // })
        }
    },
    created(){
        //Fornire i dati 
        this.getAlbums()
    }
}
</script>

<style lang="scss" scoped>

</style>
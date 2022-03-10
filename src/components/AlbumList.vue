<template>
    <section>
        <div class="container">

            <div class="album-card album">
                Album
            </div>

        </div>
    </section>
</template>

<script>
import axios from 'axios'

export default {
    name: 'AlbumList',
    data() {
        return {
            albums:[],
        }
    },
    created(){

        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( res => {
            console.log(res.data)
        } )

    }
}
</script>

<style lang="scss" scoped>

</style>
<template>
    <div>
        <div class="container">
            <div class="row ">
                <div class="theSpace d-flex flex-wrap">
                    <div class="col mb-3" v-for="album in listaAlbum" :key="album.author">
                        <AlbumCard :info="album"></AlbumCard>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import axios from "axios";

import AlbumCard from "./AlbumCard.vue"

export default {
    name: "DiscList",
    components: {
        AlbumCard,
    },

    data(){
        return{
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            listaAlbum: [],
            success: true,
        };
    },
    methods:{
        fetchDiscList() {
            axios.get(this.apiUrl).then((oggetto) => {

                this.listaAlbum = oggetto.data.response
            });
        },

    },
    //questo indica che la funzione viene avviata 
    mounted(){
        this.fetchDiscList()
    }
};
</script>


<style scoped>
    .theSpace{
        padding: 200px;
    }
</style>
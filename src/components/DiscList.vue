<template>
    <div>
        <div class="container">
            <div>
                <SearchAlbum @search="ricercaEffettuata" @reset="resetEffettuato"></SearchAlbum>
            </div>
            <div class="row ">
                <div class="theSpace d-flex flex-wrap">
                    <div class="col mb-3" v-for="album in listaAlbum" :key="album.response">
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
import SearchAlbum from "./SearchAlbum.vue"

export default {
    name: "DiscList",
    components: {
        AlbumCard,
        SearchAlbum
    },

    data(){
        return{
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            listaAlbum: [],
            success: true,
        };
    },
    methods:{
        fetchDiscList(searchAlbum) {
            axios.get(this.apiUrl, {
                params: {
                    author: searchAlbum,
                }
            }).then((oggetto) => {

                this.listaAlbum = oggetto.data.response
            })
            .catch(() => {
                this.listaAlbum = []
            });
        },
        ricercaEffettuata(searchAlbum){
            this.fetchDiscList(searchAlbum)
        },
        resetEffettuato(){
            this.fetchDiscList()
        }

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
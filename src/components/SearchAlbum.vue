<template>
<div class="d-inline-block mt-4">
    <form class="d-flex" @submit.prevent="sceltaUtente">
        <input class="form-control me-2" type="text" v-model="searchAlbum" placeholder="Cerca il tuo Album..." >
        <button class="btn btn-outline-success" type="button" @click="sceltaUtente">Search</button>
        <button class="btn btn-outline-warning" type="button" @click="resetDato">Cancella</button>
    </form>
</div>
</template>


<script>

export default {
    data() {
        return {
            searchAlbum: "",
        }
    },
    methods:{
        sceltaUtente(){
            this.$emit("search", this.searchAlbum)
        },
        resetDato(){
            this.$emit("reset")
        }
    }
}
</script>


<style scoped>

</style>
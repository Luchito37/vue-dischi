<template>
    <div>
        <div class="card cardSpace bgCard shadow-lg border border-5 border-success" style="width: 10rem;">
            <img :src="info.poster" class="card-img-top" alt="info.title">
            <div class="card-body text-white">
                <h5>{{info.title}}</h5>
                <hr>
                <div>{{info.author}}</div>
                <div>Genere : {{info.genre}}</div>
                <hr>
                <div><small>Data uscita : {{info.year}}</small></div>
            </div>
        </div>  
    </div>
</template>

<script>
export default {
    name: "AlbumCard",
    props: {
        info: Object
    }
}
</script>


<style scoped>
    .cardSpace{
        padding: 10px;
    }
    .bgCard{
            background: linear-gradient(316deg, rgb(46 46 46) 0%, rgb(0 0 0) 100%);
    }
</style>
<template>
    <div class="poster-wrapper">
        <SingleElement  v-for="movie in movieList"
        :poster = "movie.poster_path"
        :title = "movie.title"
        :name = "movie.name"
        :originalTitle = "movie.original_title"
        :originalName = "movie.original_name"
        :originalLanguage = "movie.original_language"
        :voteAverage = "movie.vote_average"
        :overview = "movie.overview"
        />
    </div>
</template>

<script>
import SingleElement from './SingleElement.vue'

export default {

    name: 'WatchList',

    components: {
        SingleElement
    },
    props : {
        movieList : Array
    }
}
</script>

<style lang="scss" scoped>
    .poster-wrapper {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
</style>
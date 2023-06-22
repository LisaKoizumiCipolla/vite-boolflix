<template>
    <div>
        <h2>WatchList</h2>
        <SingleElement  v-for="movie in movieList"
        :title = "movie.title"
        :originalTitle = "movie.original_title"
        :originalLanguage = "movie.original_language"
        :voteAverage = "movie.vote_average"
        />
    </div>
</template>
<script>
import SingleElement from './SingleElement.vue'

export default {
    
    components: {
        SingleElement
    },
    props : {
        movieList : Array
    }
}
</script>
<style lang="scss" scoped>
    
</style>
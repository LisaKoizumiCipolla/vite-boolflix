<template>
    <div>
        <h1>
            AppMain
        </h1>
        <SearchElement @search="searchedSomethingToWatch" />
        <WatchList :movieList = "movieList" />
    </div>
</template>

<script>
import WatchList from './WatchList.vue';
import axios from 'axios';
import SearchElement from './SearchElement.vue'

export default {

    components: {
        WatchList,
        SearchElement
    },

    data(){
        return {
            movieApiUrl : "https://api.themoviedb.org/3/search/movie" ,
            seriesApiUrl : "https://api.themoviedb.org/3/search/tv",
            moviesList : [],
            seriesList : [],
            movieList : [].concat(moviesList, seriesList),
            languages : ["de", "fr", "en", "it", "ja", "es", "ko", "zh", "id", "ru", "pl"]
        }
    },
    
    methods:{
        searchedSomethingToWatch(input = ""){
            
        axios.get(this.movieApiUrl, {
            params: {
                query : input,
                api_key : "db24a133b233244270659525c833dc4b"
            }
        })
        .then( (response) => {
            this.moviesList = response.data.results;
            console.log(response.data.results);

            
        })
        .catch(function (error) {
            console.log(error);
        });

        axios.get(this.seriesApiUrl, {
            params: {
                query : input,
                api_key : "db24a133b233244270659525c833dc4b"
            }
        })
        .then( (response) => {
            this.seriesList = response.data.results;
            console.log(response.data.results);

            
        })
        .catch(function (error) {
            console.log(error);
        });
        }
    },

    created(){
    }

}

</script>

<style lang="scss">
    
</style>
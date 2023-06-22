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
            movieList : [],
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
            this.movieList = response.data.results;
            console.log(response.data.results);
            console.log(response.data.results.original_language);

            
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
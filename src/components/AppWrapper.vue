<template>
        <div class="background" >
            <div class="wrapper scroll">
                <AppHeader @search="searchedSomethingToWatch" />
                <AppMain WatchList :movieList = "movieList"/>
            </div>
        </div>
</template>

<script>
import AppHeader from './AppHeader.vue'
import AppMain from './AppMain.vue';
import axios from 'axios';

export default {
    components: {
      AppHeader,
      AppMain,
    },
   

data(){
    return {
        movieApiUrl : "https://api.themoviedb.org/3/search/movie" ,
        seriesApiUrl : "https://api.themoviedb.org/3/search/tv",
        moviesList : [],
        seriesList : [],
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

computed : {
    movieList() {
        return [...this.moviesList, ...this.seriesList] 
    }
}
}
</script>

<style lang="scss">
    .background{
        background-color: #1B1B1B;
        overflow: hidden;
        height: 100vh;
    }

    .scroll{
        height: 100%;
        overflow: hidden;
    }
</style>
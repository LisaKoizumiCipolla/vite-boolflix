<template>
    <div>
        <h1>
            AppMain
        </h1>
        <SearchElement @search="searchedSomethingToWatch"/>
        <WatchList />
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
            apiUrl : "https://api.themoviedb.org/3/search/movie?api_key=db24a133b233244270659525c833dc4b&query" ,
            movieList : []
        }
    },
    
    methods:{
        searchedSomethingToWatch(input = ""){
            
        axios.get(this.apiUrl, {
            params: {
                original_title : input,
                num : 20
            }
        })
        .then( (response) => {
            this.movieList = response.data.results;
            console.log(response.data.results);
        })
        .catch(function (error) {
            console.log(error);
        });
        }
    },

    created(){
        axios.get(this.apiUrl, {
            params: {
                num : 20
            }
        })
        .then( (response) => {
            this.movieList = response.data.results;
            console.log(response.data.results);
        })
        .catch(function (error) {
            console.log(error);
        });
    }

}

</script>

<style lang="scss">
    
</style>
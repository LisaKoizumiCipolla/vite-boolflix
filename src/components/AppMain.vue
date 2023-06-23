<template>
    <div>
        <h1>
            AppMain
        </h1>
        <WatchList :movieList = "movieList" />
    </div>
</template>

<script>
import WatchList from './WatchList.vue';

export default {

    name: 'AppMain',

    components: {
        WatchList,
    },
    
    props : {
        movieList : Array
    }
}

</script>

<style lang="scss">
    
</style>
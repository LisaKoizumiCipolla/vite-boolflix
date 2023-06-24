<template>
    <div class="main">
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
    .main{
        width: 100%;
    }
</style>
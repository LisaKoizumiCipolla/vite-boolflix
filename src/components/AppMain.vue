<template>
    <div>
        <h1>
            AppMain
        </h1>
        <SearchElement />
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
    }

}

</script>

<style lang="scss">
    
</style>
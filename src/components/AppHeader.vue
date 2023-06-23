<template>
    <div>
        <h2>
            AppHeader
        </h2>
        <SearchElement @search="searchedSomethingToWatch" />
    </div>
</template>
<script>
import SearchElement from './SearchElement.vue'

export default {

    name: 'AppHeader',

components: {
    SearchElement
},

    
}
</script>
<style lang="scss">
    
</style>
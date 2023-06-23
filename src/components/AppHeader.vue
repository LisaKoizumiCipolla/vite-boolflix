<template>
    <div>
        <h2>
            AppHeader
        </h2>
        <SearchElement @search="submit" />
    </div>
</template>
<script>
import SearchElement from './SearchElement.vue'

export default {

    name: 'AppHeader',

components: {
    SearchElement
},

props : {

},

methods : {
    submit( cosa ) {
        this.$emit( 'search', cosa )
    }
}

    
}
</script>
<style lang="scss">
    
</style>
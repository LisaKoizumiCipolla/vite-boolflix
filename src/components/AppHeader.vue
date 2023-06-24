<template>
    <div>
        <div>
            <img src="../assets/icon_boolflix/boolflix_logo.png" alt="">
        </div>
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
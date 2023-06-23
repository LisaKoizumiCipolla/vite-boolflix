<template>
    <div class="input-group mb-3 searchbar">
        <span @click="$emit('search', searchedItem)" class="input-group-text" id="basic-addon1">Search</span>
        <input type="text" class="form-control" placeholder="Let's binge!" aria-label="Username" aria-describedby="basic-addon1" 
        v-model="searchedItem" @keyup.enter="$emit('search', searchedItem)">
    </div>
</template>
<script>
export default {
    name: 'SearchElement',
    
    data(){
        return {
            searchedItem : ''
        }
    }
}
</script>
<style lang="scss" scoped>
    .searchbar{
        width: 500px;
    }
</style>
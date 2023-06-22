<template>
    <div class="wrapper">
        <div v-if="name = true ?  name  :  title ">
            <div>
                {{ name }}
            </div>
            <div>
            {{ title }}</div>
        </div>
        <div v-if="originalName = true ?  originalName  :  originalTitle ">
            <div>
                {{ originalName }}
            </div>
            <div>
            {{ originalTitle }}</div>
        </div>
        <div>
            <div v-if="!languages.includes(originalLanguage)">{{ originalLanguage }}</div>
            <img :src="`/public/flags/${originalLanguage}.png`" alt="">
            
        </div>
        <div>
            {{ voteAverage }}
        </div>
    </div>
</template>
<script>
export default {
    props : {
        title : String,
        name : String,
        originalTitle : String,
        originalName : String,
        originalLanguage : String,
        voteAverage : Number
    },

    data(){
        return {
            languages : ["de", "fr", "en", "it", "ja", "es", "ko", "zh", "id", "ru", "pl"]
        }
    }
}
</script>
<style lang="scss" scoped>
    .wrapper{
        padding-bottom: 20px;
    }

    img{
        height: 30px;
    }
</style>
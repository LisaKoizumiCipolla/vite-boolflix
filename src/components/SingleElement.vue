<template>
    <div class="wrapper">
        <div>
            <div v-if="name">
                {{ name }}
            </div>
            <div v-else>
            {{ title }}</div>
        </div>
        <div>
            <div v-if="originalName">
                {{ originalName }}
            </div>
            <div v-else>
            {{ originalTitle }}
            </div>
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
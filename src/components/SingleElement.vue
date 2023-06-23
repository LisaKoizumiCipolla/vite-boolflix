<template>
    <div class="wrapper">
        <img class="poster" :src="`https://image.tmdb.org/t/p/w500/${poster}`" alt="">
        <div>
            <div v-if="name">
                {{ name }}
            </div>
            <div v-else>
                {{ title }}
            </div>
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
            <img v-else class="flag" :src="`/public/flags/${originalLanguage}.png`" alt="">
            
        </div>
        <div>
            {{ Math.ceil(voteAverage / 2) }}
            <i v-for="star in Math.ceil(voteAverage / 2)" class="fa-solid fa-star"></i>
            <i v-for="star in ( 5 - (Math.ceil(voteAverage / 2)))" class="fa-regular fa-star"></i>
        </div>
    </div>
</template>

<script>
export default {

    name: 'SingleElement',

    props : {
        poster : String,
        title : String,
        name : String,
        originalTitle : String,
        originalName : String,
        originalLanguage : String,
        voteAverage : Number
    },

    data(){
        return {
            languages : ["de", "fr", "en", "it", "ja", "es", "ko", "zh", "id", "ru", "pl"],
        }
    },

    created() {
        
    }
}
</script>

<style lang="scss" scoped>
    .wrapper{
        padding-bottom: 20px;
    }

    .poster{
        height: 350px;
    }
    .flag{
        height: 30px;
    }
</style>
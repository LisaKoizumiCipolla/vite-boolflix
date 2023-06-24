<template >

        <div class="card">
            <div class="poster-wrapper">
                <img v-if="poster" class="poster" :src="`https://image.tmdb.org/t/p/w500/${poster}`" alt="">
                <img v-else class="placeholder" src="https://www.runningin.info/wp-content/uploads/2018/07/no-image.jpg" alt="">
            </div>
            <div class="info">
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
                    <div>
                        {{ overview }}
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
        voteAverage : Number,
        overview : String
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


    .info{
        position: absolute;
        opacity: 0;
        overflow-y: auto;
        padding: 10px;
    }
    .card{
        width: calc((100% / 6) - 10px);
        border: none;
        margin-bottom: 20px;

            &:hover{
                cursor: pointer;
            }
            &:hover .info{
                opacity: 1;
                color: white;
            }

            &:hover .poster{
                opacity: .5;
            }
    }

    .poster-wrapper{
        width: 100%;
        height: 100%;
        position: relative;
        background-color: rgba(0, 0, 0);

        .poster, .placeholder{
            display: block;
            width: 100%;
        }
    }

    .placeholder{
        object-fit: cover;
        height: 100%;
    }

    .flag{
        height: 30px;
    }
</style>
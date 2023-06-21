<template>
    <div class="wrapper">
        <div>
            {{ title }}
        </div>
        <div>
            {{ originalTitle }}
        </div>
        <div>
            {{ originalLanguage }}
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
        originalTitle : String,
        originalLanguage : String,
        voteAverage : Number
    }
}
</script>
<style lang="scss" scoped>
    .wrapper{
        padding-bottom: 20px;
    }
</style>
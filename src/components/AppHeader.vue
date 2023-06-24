<template>
    <div>
        <nav>
            <div class="d-flex align-items-center">
                <img src="../assets/icon_boolflix/boolflix_logo.png" alt="">
                <ul class="d-flex align-items-center">
                    <li>Home</li>
                    <li>Serie TV</li>
                    <li>Film</li>
                    <li>Original</li>
                    <li>Aggiunti di recente</li>
                    <li>Le mie liste</li>
                </ul>
            </div>
            <div class="d-flex align-items-center">
                <ul class="d-flex align-items-center">
                    <li><i class="fa-solid fa-magnifying-glass fa-lg"></i></li>
                    <li>BAMBINI</li>
                    <li><i class="fa-solid fa-bell fa-lg"></i></li>
                    <li><img class="avatar" src="https://upload.wikimedia.org/wikipedia/commons/0/0b/Netflix-avatar.png" alt=""></li>
                    <li class="arrow"><i class="fa-solid fa-sort-down fa-2xs"></i></li>
                </ul>
                
                <span></span>
                
                
            </div>
        </nav>
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

    nav {
        color: white;
        display: flex;
        justify-content: space-between;
    }

    ul{
        list-style-type: none;

        li{
            padding: 16px 10px 0;
            font-weight: 500;
            color: rgb(219, 215, 215);

            &:hover{
                cursor: pointer;
                color: white;
            }
        }
    }

    .avatar{
        height: 40px;
        width: 40px;
    }

    .arrow{
        padding-left: 5px;
    }

</style>
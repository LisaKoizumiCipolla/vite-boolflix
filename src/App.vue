<script>
import AppMain from './components/AppMain.vue';
import {store} from '../store'

export default {
    name: 'App',

    components:{
      AppMain,
      
    }
}
</script>

<template>
  <AppMain />
</template>

<style lang="scss">

  @import "./styles/general.scss";
  @import "bootstrap/scss/bootstrap";

</style>

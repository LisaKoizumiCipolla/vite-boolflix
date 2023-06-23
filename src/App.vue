<script>
import AppWrapper from '../src/components/AppWrapper.vue'
import {store} from '../store'

export default {
    name: 'App',

    components:{
      AppWrapper
    }
}
</script>

<template>
  <AppWrapper />
</template>

<style lang="scss">

  @import "./styles/general.scss";
  @import "bootstrap/scss/bootstrap";

</style>

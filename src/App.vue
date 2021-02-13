<template>
    <BbbSeguidores msg="Welcome to Your Vue.js App"/>
</template>

<script>
import BbbSeguidores from './components/BbbSeguidores.vue'
require('../node_modules/bootstrap/dist/js/bootstrap')
require('../node_modules/bootstrap/dist/css/bootstrap.min.css')

export default {
  name: 'App',
  components: {
    BbbSeguidores
  }
}
</script>
<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>    <Titulo texto="Otro Titulo "/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Titulo from '../components/Titulo.vue'
export default {
  name: 'Home',
  components: {
    HelloWorld, Titulo  
  }
}
</script>

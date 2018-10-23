<template>
  <div class="home">
    <img class="logo" alt="Vue logo" src="../assets/wordcamp-logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>

<style lang="scss">
  .logo {
    max-width: 200px;
  }
</style>

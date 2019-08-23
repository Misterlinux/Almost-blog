<template>
  <div id="app">
    <div>
        <home testo="ok so this is where we will get the coding next"/>
        <router-link :to="{name: 'coding', params: {id: 2}}"> show the code </router-link>
        <router-view/>
    </div>
  </div>
</template>

<script>

import home from './views/Home.vue'

export default {
  name: 'app',
  components: {
    home
  }
}

</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 90vw;
  margin: 0 auto;
}

</style>

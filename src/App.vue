<template>
  <Home :title="title"/>
</template>

<script>
import Home from './components/Home.vue'

export default {
  name: 'App',
  data() {
    return {
      title: "Dota 2 Heroes"
    }
  },
  components: {
    Home
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

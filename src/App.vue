<template>
  <div id="app">
    <card/>
  </div>
</template>

<script>
import Card from './components/card'

export default {
  name: 'App',
  components: {
    Card
  }
}
</script>

<style>
html {
  background-image: url(./assets/cover.jpg);
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

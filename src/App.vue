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
body, html {
  height: 100%;
  margin: 0;
  padding: 0;
}
html {
  background-image: url(./assets/cover.jpg);
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
}
</style>

<template>
  <div id="app">
    <img src="./assets/logo.png">
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
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

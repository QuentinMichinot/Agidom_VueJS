<template>
  <div id="app">
    <polaroid />
    <div class="agidom-start">
      <button @click="initAgidom()" class="agidom-btn-start">
        <img src="./assets/start.png" alt="" id="agidom-image-start">
      </button>
    </div>
    <cards>
      <card v-for="n in cards" :index="n - 1" :key='n' class="card-images" url="http://loremstudio.com/wp-content/uploads/avatar-1.png"></card>
    </cards>
    <!-- <FormCard /> -->
  </div>
</template>

<script>
import Card from './components/card/Card'
import Cards from './components/card/Cards'
import Polaroid from './components/polaroid/polaroid'
import FormCard from './components/FormCard/FormCard'

export default {
  name: 'App',
  components: {
    Card,
    Cards,
    Polaroid,
    FormCard
  },
  data () {
    return {
      cards: 0
    }
  },
  methods: {
    addCard () {
      if (this.cards < 14) {
        this.cards++
      }
    },
    initAgidom () {
      var element = document.getElementById('agidom-image-start')
      element.classList.toggle('active-start-btn')
      setTimeout(function () {
        element.classList.remove('active-start-btn')
      }, 350)
    }
  }
}
</script>

<style lang="scss">
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
  padding-top: 20px;
}
.agidom-start {
  width: 300px;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  button {
    background: transparent;
    border: transparent;

    &:active {
      border: transparent;
    }
    &:focus {
      outline:0;
    }
  }
  img {
    width: 300px;
    transition-duration: 0.3s;
  }
  .active-start-btn {
    transform: rotate3d(1, 1, 1, -30deg);
  }
}
</style>

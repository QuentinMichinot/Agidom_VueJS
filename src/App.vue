<template>
  <div id="app">
    <polaroid />
    <div class="agidom-start">
      <button @click="initAgidom()" class="agidom-btn-start">
        <img src="./assets/start.png" alt="" id="agidom-image-start">
      </button>
    </div>
    <cards :cards="cards" />
    <!-- <FormCard /> -->
  </div>
</template>

<script>
import Cards from './components/card/Cards'
import Polaroid from './components/polaroid/polaroid'
import FormCard from './components/FormCard/FormCard'

export default {
  name: 'App',
  components: {
    Cards,
    Polaroid,
    FormCard
  },
  data () {
    return {
      cards: [{
        name: 'Tom',
        url: 'https://yt3.ggpht.com/a-/AAuE7mD5Xx-dvJZK9zR6G5oUjzZDgv5jSp8WTvuPOg=s288-mo-c-c0xffffffff-rj-k-no'
      }, {
        name: 'Quentin',
        url: 'data:image/jpeg;base64,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'
      }]
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

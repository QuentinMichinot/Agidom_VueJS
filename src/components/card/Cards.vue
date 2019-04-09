<template>
  <div class="cards">
    <card
      v-for="(card, index) in cards"
      :key="index"
      class="card-images"
      :url="card.url"
      :name="card.name"
    />
  </div>
</template>

<script>
import card from './Card'

export default {
  components: {
    card
  },
  props: ['cards']
}
</script>

<style lang="scss">
.cards {
  margin-top: 20px;
  width: 100%;
  position: absolute;
  top: 350px;
}
</style>

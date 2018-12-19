<template>
  <div class="add_car">
    <h2 class="title_add_car">Ajouter un Avatar</h2>
    <input type="text" id="itemFormSrc" placeholder="Lien de l'image">
    <input type="text" id="itemFormName" placeholder="Nom">
    <button @click="addItem" type="submit">Ajouter</button>
  </div>
</template>

<script>
import Card from '../card/card'

export default {
  name: 'FormCard',
  components: {
    Card
  },
  methods: {
    addItem: function () {
      var inputSrc = document.getElementById('itemFormSrc')
      var inputName = document.getElementById('itemFormName')

      if (inputSrc.value !== '' && inputName.value !== '') {
        this.items.push({
          image: inputSrc.value,
          name: inputName.value
        })
        inputSrc.value = ''
        inputName.value = ''
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.add_car {
  width: 25%;
  background-color: rgba(0, 0, 0, 0.5);
  padding: 50px;
  top: 0;
  position: absolute;
  right: 0;

  input {
    border: none;
    width: 95%;
    margin: 0 0 15px 0;
    padding: 10px;
  }
  button {
    width: 99%;
    padding: 10px;
    border: none;
  }
  .title_add_car {
    color: white;
  }
}
</style>

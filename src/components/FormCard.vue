<template>
  <div class="add_car">
    <h2 class="title_add_car">Ajouter un Avatar</h2>
    <input type="text" id="itemFormSrc" v-on:keypress.enter="addItem" placeholder="Lien de l'image">
    <br>
    <input type="text" id="itemFormName" v-on:keypress.enter="addItem" placeholder="Nom">
    <br>
    <button v-on:click="addItem">Ajouter</button>
  </div>
</template>

<script>
export default {
  name: 'FormCard'
}
</script>

<style lang="scss" scoped>
.add_car {
  position: absolute;
  right: 0;
  background-color: rgba(0, 0, 0, 0.5);
  padding: 50px;
  top: 0;

  input {
    width: 100%;
    margin: 0 0 15px 0;
    padding: 5px;
  }
  .title_add_car {
    margin: 0 0 15px 0;
    color: white;
  }
}
</style>

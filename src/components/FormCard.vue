<template>
  <div class="add_car">
    <label for="itemFrom">Lien d'image</label>
    <input type="text" id="itemFormSrc" v-on:keypress.enter="addItem">
    <br>
    <label for="itemFormName">Nom</label>
    <input type="text" id="itemFormName" v-on:keypress.enter="addItem">
    <br>
    <button v-on:click="addItem">Ajouter</button>
  </div>
</template>

<script>
export default {
  name: 'FormCard'
}
</script>

<style>
.add_car {
  position: absolute;
  right: 0;
  background-color: white;
  padding: 50px;
  top: 0;
}
</style>

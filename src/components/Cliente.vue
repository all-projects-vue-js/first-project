<template>
  <div id="cliente">
    <input type="text" v-model="nome" />
    <h2>Nome: {{ cliente.nome }}</h2>
    <h2 v-if="showIdade === true">Idade: {{ cliente.idade }}</h2>
    <h2 v-else>Escondeu a idade</h2>
    <h2 v-show="showIdade">Mostrar a idade v-show</h2>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    cliente: Object,
    showIdade: Boolean,
  },
};
</script>

<style scoped>
#cliente {
  max-width: 340px;
  height: 180px;
  padding: 1%;
  margin-top: 2%;
  color: rgb(74, 141, 228);
  background-color: rgb(169, 184, 230);
}
</style>
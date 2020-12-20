<template>
  <div id="cliente">
    <input type="text" v-model="nome" />
    <h2>Nome: {{ cliente.nome }}</h2>
    <h2>Idade: {{ cliente.idade }}</h2>
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
  },
};
</script>

<style scoped>
#cliente {
  max-width: 340px;
  height: 150px;
  padding: 1%;
  margin-top: 2%;
  color: rgb(74, 141, 228);
  background-color: rgb(169, 184, 230);
}
</style>
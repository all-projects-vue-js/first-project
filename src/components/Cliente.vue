<template>
  <div id="cliente">
    <input type="text" v-model="nome" />
    <h2>Nome: {{ nome }}</h2>
    <h2>Idade: {{ idade }}</h2>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    nome: String,
    idade: Number,
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
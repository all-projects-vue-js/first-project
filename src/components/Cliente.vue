<template>
  <div id="cliente">
    <h2>Nome: {{ nome }}</h2>
    <h2>Idade: {{ idade }}</h2>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {
      nome: "Henrique Ramires",
      idade: 29,
    };
  },
};
</script>

<style scoped>
#cliente {
  max-width: 340px;
  height: 120px;
  padding: 1%;
  margin-top: 2%;
  color: rgb(74, 141, 228);
  background-color: rgb(169, 184, 230);
}
</style>
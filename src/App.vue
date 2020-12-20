<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <div v-for="(cliente, index) in clientes" :key="cliente.id">
      <h4>{{ index }}</h4>
      <input type="text" v-model="cliente.nome" />
      <Cliente :cliente="cliente" :showIdade="true" />
    </div>
  </div>
</template>

<script>
import Cliente from "./components/Cliente";
export default {
  name: "App",
  data() {
    return {
      clientes: [
        {
          id: 0,
          nome: "Henrique Ramires",
          idade: 28,
        },
        {
          id: 1,
          nome: "Fernando Moraes",
          idade: 48,
        },
        {
          id: 2,
          nome: "Paulo Andre",
          idade: 25,
        },
      ],
    };
  },
  components: {
    Cliente,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

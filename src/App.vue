<template>
  <div id="app">
    <h1>Guia Clientes</h1>
    <input type="text" v-model="clienteHenrique.nome" />
    <Cliente :cliente="clienteHenrique" />
  </div>
</template>

<script>
import Cliente from "./components/Cliente";
export default {
  name: "App",
  data() {
    return {
      clienteHenrique: {
        nome: "Henrique Ramires",
        idade: 28,
      },
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

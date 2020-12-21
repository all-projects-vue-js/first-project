<template>
  <div id="app">
    <h3>Cadastro</h3>
    <input type="text" placeholder="nome" v-model="nomeField" /> <br />
    <input type="text" placeholder="Idade" v-model="idadeField" /> <br />
    <button @click="cadastrarFuncionarios()">Cadastrar</button>
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
      nomeField: "",
      idadeField: "",
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
  methods: {
    cadastrarFuncionarios: function () {
      this.clientes.push({
        nome: this.nomeField,
        idade: this.idadeField,
        id: Date.now,
      });
      this.nomeField = "";
      this.idadeField = "";
    },
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

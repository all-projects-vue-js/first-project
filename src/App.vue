<template>
  <div id="app">
    <div class="buttons">
      <button class="button is-info">Info</button>
      <button class="button is-success">Success</button>
      <button class="button is-warning">Warning</button>
      <button class="button is-danger">Danger</button>
    </div>
    <h3>Cadastro</h3>
    <small id="nomeErro" v-show="deuErro">O nome é invalido.</small> <br />
    <input type="text" placeholder="nome" v-model="nomeField" /> <br />
    <input type="text" placeholder="Idade" v-model="idadeField" /> <br />
    <button @click="cadastrarFuncionarios()">Cadastrar</button>
    <h1>Guia Clientes</h1>
    <div v-for="(cliente, index) in orderClientes" :key="cliente.id">
      <h4>{{ index }}</h4>
      <Cliente :cliente="cliente" @meDelete="deletarUsuario($event)" />
    </div>
  </div>
</template>

<script>
import _ from "lodash";
import Cliente from "./components/Cliente";
export default {
  name: "App",
  data() {
    return {
      deuErro: false,
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
      if (
        this.nomeField == "" ||
        this.nomeField == " " ||
        this.nomeField.length < 3
      ) {
        this.deuErro = true;
        console.log("Erro de validacao");
      } else {
        this.deuErro = false;
        this.clientes.push({
          nome: this.nomeField,
          idade: this.idadeField,
          id: Date.now,
        });
        this.nomeField = "";
        this.idadeField = "";
      }
    },
    deletarUsuario: function ($event) {
      console.log("Recebendo evento");
      console.log($event.idCoCliente);
      $event.component.testar();

      var id = $event.idCoCliente;
      var novoArray = this.clientes.filter((cliente) => cliente.id != id);
      this.clientes = novoArray;
    },
  },
  computed: {
    orderClientes: function () {
      return _.orderBy(this.clientes, ["nome"], ["asc"]);
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

#nomeErro {
  color: red;
}
</style>

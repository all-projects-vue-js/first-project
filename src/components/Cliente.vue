<template>
  <div :class="{ cliente: !isPremium, 'cliente-premium': isPremium }">
    <input type="text" v-model="nome" />
    <h2>Nome: {{ cliente.nome | processarNome }}</h2>
    <h2 v-if="showIdade === true">Idade: {{ cliente.idade }}</h2>
    <h2 v-else>Escondeu a idade</h2>
    <h2 v-show="showIdade">Mostrar a idade v-show</h2>
    <button @click="mudarCor($event)">Mudar a cor</button>
    <button @click="emirtirEventoDelete()">Deletar</button>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPremium: false,
    };
  },
  props: {
    cliente: Object,
    showIdade: Boolean,
  },
  methods: {
    mudarCor: function ($event) {
      console.log($event);
      this.isPremium = !this.isPremium;
    },
    emirtirEventoDelete: function () {
      console.log("Emitindo do filho!");
      this.$emit("meDelete", { idCoCliente: this.cliente.id, component: this });
    },
    testar: function () {
      console.log("Testando para valer!");
      alert("Isso é um alert!");
    },
  },
  filters: {
    processarNome: function (value) {
      return value.toUpperCase();
    },
  },
};
</script>

<style scoped>
.cliente {
  max-width: 340px;
  height: 180px;
  padding: 1%;
  margin-top: 2%;
  color: rgb(74, 141, 228);
  background-color: rgb(169, 184, 230);
}

.cliente-premium {
  max-width: 340px;
  height: 180px;
  padding: 1%;
  margin-top: 2%;
  color: rgb(224, 210, 13);
  background-color: rgb(10, 11, 12);
}
</style>
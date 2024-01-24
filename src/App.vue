<script setup>
import { reactive } from "vue";
import Cabecalho from "./components/Cabecalho.vue";
import Operacao from "./components/Operacao.vue";
import Resultado from "./components/Resultado.vue";

const estado = reactive({
  operacao: "adicao",
  num1: "",
  num2: "",
});

const resultado = () => {
  const { operacao } = estado;
  const { num1, num2 } = estado;

  switch (operacao) {
    case "subtracao":
      return parseFloat(num1) - parseFloat(num2);
    case "divisao":
      return parseFloat(num1) / parseFloat(num2);
    case "multiplicacao":
      return parseFloat(num1) * parseFloat(num2);
    default:
      return parseFloat(num1) + parseFloat(num2);
  }
};
</script>

<template>
  <body>
    <div class="container">
    <Cabecalho></Cabecalho>
  <Operacao
    :operacao="(evento) => (estado.operacao = evento.target.value)"
    :num1="(evento) => (estado.num1 = evento.target.value)"
    :num2="(evento) => (estado.num2 = evento.target.value)"
  ></Operacao>
  <Resultado :num1="estado.num1" :num2="estado.num2" :resultado="resultado()"></Resultado>
  </div>
  </body>
</template>

<style scoped></style>

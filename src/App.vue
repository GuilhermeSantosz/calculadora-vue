<script setup>
import { reactive } from 'vue';


const conta = reactive({
  operacao: "adicao",
  num1: 0,
  num2: 0,
  });
  function adicao() {
    const {num1, num2} = conta;
    return parseInt(num1) + parseInt(num2);
  }
  function subtracao() {
    const {num1, num2} = conta;
    return parseInt(num1) - parseInt(num2);
  }
  function multiplicacao() {
    const {num1, num2} = conta;
    return parseInt(num1) * parseInt(num2);
  }
  function divisao() {
    const {num1, num2} = conta;
    return parseInt(num1) / parseInt(num2);
  }

  const getOperacao = () => {
    const {operacao} = conta;

    switch (operacao) {
      case "adicao":
        return adicao();
      case "subtracao":
        return subtracao( );
      case "multiplicacao":
        return multiplicacao();
      case "divisao":
        return divisao();
    }
    
  }
  
</script>

<template>
    <form>
    <input
      type="number"
      @keyup="(evento) => (conta.num1 = evento.target.value)"
    />
    <input
      type="number"
      @keyup="(evento) => (conta.num2 = evento.target.value)"
    />
    <select @change="getOperacao()" name="form-control">
      <option value="adicao">Adição</option>
      <option value="subtracao">Subtração</option>
      <option value="multiplicacao">Multiplicação</option>
      <option value="divisao">Divisão</option>
    </select>
    <span>Resultado: {{ getOperacao() }}</span>
  </form>
</template>

<style scoped></style>

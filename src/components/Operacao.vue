<script setup>
const props = defineProps(["operacao", "num1", "num2"]);
</script>

<template>
  <div class="text-center">
    <div class="operacao">
      <h2 class="mt-4">Selecione a operação</h2>
      <select @change="props.operacao" class="mt-2">
        <option value="adicao">Adição</option>
        <option value="subtracao">Subtração</option>
        <option value="multiplicacao">Multiplicação</option>
        <option value="divisao">Divisão</option>
      </select>
    </div>
    <div class="mt-4">
      <input
        @keyup="props.num1"
        required
        type="number"
        placeholder="Insira o número 1"
      />
      <input
        @keyup="props.num2"
        required
        type="number"
        placeholder="Insira o número 2"
      />
    </div>
  </div>
</template>

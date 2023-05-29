<script setup>
import { reactive } from 'vue';

const estado = reactive({
  numeroUm: 0,
  numeroDois: 0,
  sinal: '+',
})



const calcularResultado = () => {
  switch (estado.sinal) {
    case '+':
      return parseInt(estado.numeroUm) + parseInt(estado.numeroDois);
    case '-':
      return parseInt(estado.numeroUm) - parseInt(estado.numeroDois);
    case '/':
      return parseInt(estado.numeroUm) / parseInt(estado.numeroDois);
    case '*':
      return parseInt(estado.numeroUm) * parseInt(estado.numeroDois);
    default:
      return 0;
  }
}

</script>

<template>
  <h1>Calculadora</h1>
  <input type="number" @keyup="evento => estado.numeroUm = evento.target.value">

  <select v-model="estado.sinal">
    <option value="+">+</option>
    <option value="-">-</option>
    <option value="/">/</option>
    <option value="*">*</option>
  </select>

  <input type="number" @keyup="evento => estado.numeroDois = evento.target.value">

  <h3>Resultado: {{ calcularResultado() }}</h3>
</template>

<style scoped>
input {
  margin-right: 10px;
  
  margin-left: 10px;
}
</style>

<script setup>
import { reactive } from "vue";
import Cabecalho from "./components/Cabecalho.vue";
import Formulario from "./components/Formulario.vue";
import Resultado from "./components/Resultado.vue";
const estado = reactive({
  num1: 0,
  num2: 0,
  operacao: "",
});

const calc = () => {
  const { operacao, num1, num2 } = estado;
  switch (operacao) {
    case "+":
      return num1 + num2;
      break;
    case "-":
      return num1 - num2;
      break;
    case "*":
      return num1 * num2;
      break;
    case "/":
      return num2 !== 0 ? num1 / num2 : "Erro: divisão por zero!";
      break;
    case "%":
      return num2 !== 0 ? num1 % num2 : "Erro: resto da divisão por zero!";
      break;
    case "**":
      return num1 ** num2;
      break;
    default:
      return "Escolha uma operação";
  }
};
</script>

<template>
  <div class="container bg-light rounded-4">
    <Cabecalho />

    <Formulario
      :num1="(evento) => (estado.num1 = Number(evento.target.value))"
      :num2="(evento) => (estado.num2 = Number(evento.target.value))"
      :operacao="(evento) => (estado.operacao = evento.target.value)"
    />
    <Resultado
      :calc="calc()"
      :resultado="`${estado.num1} ${estado.operacao} ${
        estado.num2
      } = ${calc()}`"
    />
  </div>
</template>

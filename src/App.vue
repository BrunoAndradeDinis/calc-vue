<script setup>
import { reactive } from "vue";
const estado = reactive({
  resultado: "",
});

const calc = () => {
  let res;
  switch (selected.value) {
    case "+":
      return numero + numero2;
      break;
    case "-":
      return numero - numero2;
      break;
    case "*":
      return numero * numero2;
      break;
    case "/":
      return numero2 !== 0 ? numero / numero2 : "Erro: divisão por zero!";
      break;
    case "%":
      return numero2 !== 0
        ? numero % numero2
        : "Erro: resto da divisão por zero!";
      break;
    case "**":
      return numero ** numero2;
      break;
    default:
      return "Escolha uma operação";
  }
};
</script>

<template>
  <div class="container bg-light rounded-4">
    <header class="py-5 my-4">
      <h1 class="text-center">Calculadora aritmética</h1>
    </header>
    <form class="pb-3">
      <div class="row">
        <div class="col md-4">
          <input
            class="form-control"
            type="number"
            name=""
            id=""
            placeholder="Digite um número:"
          />
        </div>
        <div class="col md-4">
          <input
            class="form-control"
            type="number"
            name=""
            id=""
            placeholder="Digite um número:"
          />
        </div>
        <div class="col md-4">
          <select name="" id="" class="form-select">
            <option value="" disabled selected>Selecione uma operação</option>
            <option value="+">Adição +</option>
            <option value="-">Subtração -</option>
            <option value="*">Multiplicação X ou *</option>
            <option value="/">Divisão /</option>
            <option value="%">Resto da divisão %</option>
            <option value="**">Exponenciação ⁿ ou ¹ ou **</option>
          </select>
        </div>
      </div>
    </form>
    <main>
      <div class="container py-3 my-3 text-center">
        <h3>Resultado a operação</h3>
        <p class="my-4">Num 1 operacao Num 2 = Resultado {{ resultado }}</p>
      </div>
    </main>
  </div>
</template>

<script setup>
  const props = defineProps([
    'num1', 'num2', 'operacao'
  ]);
</script>

<template>
  <form class="pb-3">
    <div class="row">
      <div class="col md-4">
        <input
          @input="props.num1"
          class="form-control"
          type="number"
          name=""
          id=""
          placeholder="Digite um número:"
        />
      </div>
      <div class="col md-4">
        <input
          @input="props.num2"
          class="form-control"
          type="number"
          name=""
          id=""
          placeholder="Digite um número:"
        />
      </div>
      <div class="col md-4">
        <select
          @input="props.operacao"
          class="form-select"
        >
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
</template>

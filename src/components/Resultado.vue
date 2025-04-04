<script setup>
  const props = defineProps([
    "calc", "resultado"
  ])
</script>

<template>
  <main>
    <div class="container py-3 my-3 text-center">
      <h3>Resultado a operação</h3>
      <p v-if="props.calc === 'Escolha uma operação'">{{ props.calc }}</p>
      <p class="my-4" v-else>
        {{props.resultado }}
      </p>
    </div>
  </main>
</template>

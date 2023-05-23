<template>
  <div>
    <h2>Primeiro componente</h2>
    <p>Texto vindo do primeiro componente</p>
  </div>
</template>

<script>

// Exports my component.
export default {
  name: 'Component1'
}

</script>

<style scoped>
div {
  margin-top: 10px;
  border: 1px solid salmon;
  padding: 10px;
}
</style>

<template>
  <div>
    <h4>Trabalhando com o vue.</h4>
    <Component1 />
    <Component2 />
    <LifeCycle />
    <Pessoa />
  </div>
</template>

<script>
import Component1 from './components/Component1.vue'
import Component2 from './components/Component2.vue'
import LifeCycle from './components/LifeCycle.vue'
import Pessoa from './components/Pessoa.vue'

export default { 
  components: { 
    Component1,
    Component2,
    LifeCycle,
    Pessoa
    } 
  }
</script>

<style scoped>

</style>

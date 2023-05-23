<template>
  <div>
    <h2>Segundo componente</h2>
    <div>
        <p>Contador</p>
        <button @click="incrementCounter">{{ count }}</button>
    </div>
  </div>
</template>

<script>
export default { 
    name: 'Component2', 
    data() {
        return {
            count: 0
        }
    },
    methods: {
        // Solução para salvar o dado em coockie, será utilizado 2 funções, uma delas setará o valor e a outra irá pegar, depois de tudo feito chamo minha função mounted.
        incrementCounter() {
            this.count++
            localStorage.setItem('contador', this.count.toString())
        },
        retriveCounter() {
            const savedCount = localStorage.getItem('contador');
            savedCount ? this.count = parseInt(savedCount) : null
        }
    },
    mounted() {
        this.retriveCounter()
    }
    }
</script>

<style scoped>
div {
    display: flex;
    flex-direction: column;
    align-items: center;
    border: 1px solid black;
    padding: 7px;
}
button {
    width: 100px;
    border: 1px solid transparent;
    cursor: pointer;
}
button:focus:hover {
    border: 1px solid black;
}
</style>
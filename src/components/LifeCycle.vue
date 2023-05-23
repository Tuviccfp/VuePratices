<template>
    <div>
        <h1>Meu nome é: {{ `${nome} ${sobrenome}`}}</h1>
    </div>
</template>

<script>

export default {
    name: "LifeCycle",
    // Função disponível que gera um valor a partir do vue, um valor "padrão".
    data() {
        return {
            nome: "Ainda não sei",
            sobrenome: "Ainda não sei"
        }
    },
    created() {
        // Quando o elemento for criado, esse hook será executado.
        setTimeout(() => {
            this.nome = "Victor"
            this.sobrenome = "Cordeiro"
        }, 1000)
    },
    mounted() {
        // Quando o elemento é montado, esse hook será executado.
        setTimeout(() => {
            this.nome = "Ana"
            this.sobrenome = "Silva"
        }, 2500)
    }

}

</script>

<style scoped>
div {
    border: 1px solid black;
    padding: 7px;
}
</style>
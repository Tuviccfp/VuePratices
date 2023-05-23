<template>
    <div>
        <h3>Esta é a descrição da pessoa: {{ nome }}</h3>
        <p>{{ `${work ? 'Estou trabalhando no momento.' : 'No momento não estou trabalhando.'}` }}</p>
        <button @click="toggleWork">{{ work ? "Off" : "On" }}</button>
        
        <template v-if="info">
            <Info />
        </template>
        <button @click="toggleInfo">{{!info ? "Exibir infos" : "Ocultar"}}</button>
    </div>
</template>

<script>
import Info from './Info.vue'

export default {
    name: 'Pessoa',
    data() {
        return {
            nome: "Victor",
            work: true,
            info: false
        }
    },
    components: {
        Info
    },
    methods: {
        toggleWork() {
            this.work = !this.work
        },
        toggleInfo() {
            this.info = !this.info
        }
    }
}

</script>

<style scoped>
div {
    border: 1px solid black;
    padding: 7px;
    display: flex;
    flex-direction: column;
    align-items: center;
}
button {
    margin-bottom: 5px;
}
#info {
    border: none;
}
</style>
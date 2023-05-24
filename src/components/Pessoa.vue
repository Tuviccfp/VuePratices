<template>
    <div>
        <h3>Esta é a descrição da pessoa: {{ nome }}</h3>
        <img :style="`width: ${width_avatar}; height: ${height_avatar};`" :src="avatar_url" :alt="alt_img" />
        <p>Meu portifólio: <a :href="link_url">{{ link_url }}</a></p>
        <p>{{ `${work ? 'Estou trabalhando no momento.' : 'No momento não estou trabalhando.'}` }}</p>
        <button @click="toggleWork">{{ work ? "Off" : "On" }}</button>
        
        <div v-show="info">
            <Info />
        </div>
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
            info: false,
            avatar_url: "https://png.pngtree.com/element_our/png_detail/20181208/male-student-icon-png_265268.jpg",
            alt_img: "icon-user",
            width_avatar: '150px',
            height_avatar: '150px',
            link_url: "https://www.google.com.br"
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

<!-- 
    *Utilização das diretivas v-if, v-else, v-show.
As diretivas if e else, são para quando tenho dados que precisam retonar caso eu obtenha uma condição entre elas.
Já a v-show apesar de ser bastante parecida com as diretivas if e else, são diferentes uma da outra, já que a v-show altera a visibilidade do elemento, 
alterando seu atributo CSS display para none. 

    *Atributos dinâmicos v-bind:atributo="expressão" ou :atributo="expressão"
Permite vincular dinamicamente um valor a um atributo HTML, uma classe CSS ou um estilo, usado para interligar dados vindo do Vue que serão utilizados no html ou em seus atributos. 
-->
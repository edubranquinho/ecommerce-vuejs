<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1></h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>

    {{valorTotal}}
  
    <botao :descricao=" 'Comprar aqui 2!' " @botao-clicado="comprarProduto" ></botao>

    <botao :descricao=" 'Devolução aqui!' " @botao-clicado="devolucaoProduto" ></botao>

    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>

import Botao from './shared/Botao.vue';

export default {
  components: { Botao },
  name: 'app',
  data() {
     return {
       produto: {
          quantidade: 10,
          preco: 3
       }
    }
  },
  filters: {
    toUpperCase(texto) {
      return texto.toUpperCase();
    }
  },
  methods: {
    comprarProduto() {
      console.log('Produto comprado');
    },
    devolucaoProduto() {
      console.log('Produto devolvido');
    }
  },

  computed: {
    valorTotal() {
        return this.produto.quantidade * this.produto.preco;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

<template>
  <div>
      <button @click="botaoClicado()"> {{descricao}} </button>
  </div>
</template>

<script>
export default {
  name: 'Botao',
  props: {
    descricao: String
  },

  methods: {
    botaoClicado() {
      this.$emit('botao-clicado');
    }
  }
}
</script>

<style>

button {
  color: #1a0285;
}
</style>

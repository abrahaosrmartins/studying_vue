<template>
  <h1>Componente App</h1>
  <topo-padrao />
  <conteudo />
</template>

<script>
import Conteudo from '@/components/layouts/Conteudo.vue';
import TopoPadrao from '@/components/layouts/TopoPadrao.vue';

export default {
  name: 'App',
  components: {
    Conteudo, //TODO: Confirmar informação: A partir do ES6, podemos usar tanto a sintaxe enxuta ({ Conteúdo }), quanto o padrão chave: valor ({Conteudo: Conteudo})
    TopoPadrao
  }
}
</script>

<style>
</style>

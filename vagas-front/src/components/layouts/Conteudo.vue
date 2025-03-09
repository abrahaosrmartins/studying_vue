<template>
    <div>
        <h1>Componente Conteúdo</h1>
        <home />
        <publicar-vaga />
    </div>
</template>

<script>
import Home from '@/components/views/Home.vue';
import PublicarVaga from '@/components/views/PublicarVaga.vue';

export default {
    name: 'Conteudo',
    components: {
        Home,
        PublicarVaga
    }
}
</script>

<style>
</style>
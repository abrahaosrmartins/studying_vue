<template>
    <div>
        <h1>Componente Conteúdo</h1>
        <!-- renderizar de modo dinâmico os componentes home e publicar-vaga -->
        <button>Atualizar</button>
        <button @click="conteudo = 'home'">Home</button>
        <button @click="conteudo = 'publicar-vaga'">Publicar Vaga</button>
        <keep-alive>
            <component :is="conteudo" />
        </keep-alive>
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
    },
    data: () => ({
        conteudo: 'home'
    }),
    // methods: {
    //     // code
    // },
    // beforeCreate() {
    //     console.log('Antes de criar');
    // },
    // created() {
    //     console.log('Criado');
    // },
    // beforeMount() {
    //     console.log('Antes de montar');
    // },
    // mounted() {
    //     console.log('Montado');
    // },
    // beforeUpdate() {
    //     console.log('Antes de atualizar');
    // },
    // updated() {
    //     console.log('Atualizado');
    // },
    // beforeUnmount() {
    //     console.log('Antes de desmontar');
    // },
    // unmounted() {
    //     console.log('Desmontado');
    // },
    // errorCaptured() {
    //     console.log('Erro capturado');
    // },
    // renderTracked() {
    //     console.log('Re-renderizado');
    // },
    // renderTriggered() {
    //     console.log('Re-renderização acionada');
    // },
    // activated() {
    //     console.log('Componente é ativado');
    // },
    // deactivated() {
    //     console.log('Componente é desativado');
    // }
}
</script>

<style>
</style>
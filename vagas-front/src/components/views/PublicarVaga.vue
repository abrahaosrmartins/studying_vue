<template>
    <div>
        <h1>Componente Publicar Vaga</h1>
    </div>
</template>

<script>
export default {
    name: 'Publicar Vaga',
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
    beforeUnmount() {
        console.log('Antes de desmontar');
    },
    unmounted() {
        console.log('Desmontado');
    },
    // errorCaptured() {
    //     console.log('Erro capturado');
    // },
    // renderTracked() {
    //     console.log('Re-renderizado');
    // },
    // renderTriggered() {
    //     console.log('Re-renderização acionada');
    // },
    activated() {
        console.log('Componente é ativado');
    },
    deactivated() {
        console.log('Componente é desativado');
    }
}
</script>

<style></style>
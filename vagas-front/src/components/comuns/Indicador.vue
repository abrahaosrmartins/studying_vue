<template>
    <div :class="estilo">
        <p>{{ titulo }}</p>
        <h2>{{ indicador }}</h2>
    </div>
</template>

<script>
export default {
    name: 'Indicador',
    props: [
        'titulo',
        'indicador',
        'bg',
        'color'
    ],
    computed: {
        estilo() {
            return `h-100 p-5 rouded-3 border ${this.bg} ${this.color}`
        }
    }
}
</script>
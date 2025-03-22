<template>
    <div :class="estilo">
        <p>{{ titulo }}</p>
        <h2>{{ indicador }}</h2>
    </div>
</template>

<script>
export default {
    name: 'Indicador',
    props: {
        titulo: {
            type: String,
            default: ''
        },
        indicador: {
            type: String,
            default: ''
        },
        bg: {
            type: String,
            default: ''
        },
        color: {
            type: String,
            default: ''
        },
    },
    computed: {
        estilo() {
            return `h-100 p-5 rouded-3 border ${this.bg} ${this.color}`
        }
    }
}
</script>
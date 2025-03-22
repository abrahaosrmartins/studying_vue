<template>
    <div class="card">
        <div class="card-header bg-dark text-white">{{ tituloVagaTeste }}</div>
        <div class="card-body">
            <p>{{ descricaoVaga }}</p>
        </div>
        <div class="card-footer">
            <small class="text-muted">
                Salário: {{ salario }} | Modalidade: {{ modalidade }} | Tipo: {{ tipo }} | Publicação: {{ publicacao }}
            </small>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Vaga',
    props: {
        tituloVagaTeste: {
            type: String,
            default: '',
            required: true,
            validator(p) { // recebe a prop por padrão
                if (p.length < 6) {
                    return false // se for inválida
                }
                return true; // se for válida
                //return false se for inválida
            }
        },
        descricaoVaga: {
            type: String,
            default: '',
            required: true
        },
        salario: {
            type: [Number, String],
            default: 0,
            required: true
        },
        modalidade: {
            type: String,
            default: '',
            required: true
        },
        tipo: {
            type: String,
            default: '',
            required: true
        },
        publicacao: {
            type: String,
            default: '',
            required: true
        },
    }
}
</script>
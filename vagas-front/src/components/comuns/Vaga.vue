<template>
    <div class="card">
        <div class="card-header bg-dark text-white">{{ titulo }}</div>
        <div class="card-body">
            <p>{{ descricao }}</p>
        </div>
        <div class="card-footer">
            <small class="text-muted">
                Salário: {{ salario }} | Modalidade: {{ modalidade }} | Tipo: {{ tipo }} | Publicação: {{ formataDataDePublicacao(publicacao) }}
            </small>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Vaga',
    props: {
        titulo: {
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
        descricao: {
            type: String,
            default: 'Não informada',
        },
        salario: {
            type: [Number, String],
            default: 0,
        },
        modalidade: {
            type: String,
            default: 'Não informada',
        },
        tipo: {
            type: String,
            default: 'Não informado',
        },
        publicacao: {
            type: String,
            default: 'Não informada',
        },
    },
    methods: {
        formataDataDePublicacao(data) {
            const meses = [
                'Janeiro',
                'Fevereiro',
                'Março',
                'Abril',
                'Maio',
                'Junho',
                'Julho',
                'Agosto',
                'Setembro',
                'Outubro',
                'Novembro',
                'Dezembro'
            ];
            const dataNoFormatoArray = data.split('-');

            return `${dataNoFormatoArray[2]} de ${meses[dataNoFormatoArray[1] - 1]} de ${dataNoFormatoArray[0]}`
        }
    }
}
</script>
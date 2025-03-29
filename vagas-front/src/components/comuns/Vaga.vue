<template>
    <div class="card">
        <div class="card-header bg-dark text-white">{{ titulo }}</div>
        <div class="card-body">
            <p>{{ descricao }}</p>
        </div>
        <div class="card-footer">
            <small class="text-muted">
                Salário: {{ salario }} | Modalidade: {{ getModalidade }} | Tipo: {{ getTipo }} | Publicação: {{ getPublicacao }}
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
    computed: {
        getPublicacao() {
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
            const data = this.publicacao.split('/');

            return `${data[0]} de ${meses[data[1] - 1]} de ${data[2]}`
        },
        getModalidade() {
            switch (this.modalidade) {
                case '1': return 'Home Office';
                case '2': return 'Presencial'
            }
            return 'Não informada';
        },
        getTipo() {
            switch (this.modalidade) {
                case '1': return 'CLT';
                case '2': return 'PJ'
            }
            return 'Não informado';
        },
    }
}
</script>
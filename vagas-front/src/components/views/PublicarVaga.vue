<template>
    <div class="container py-4">
        <div class="row">
            <div class="col">
                <h4>Apresente a sua vaga para milhares de profissionais e de graça</h4>
            </div>
        </div>

        <div class="row mt-3">
            <div class="col">
                <label class="form-label">Título da Vaga</label>
                <input type="text" class="form-control" v-model="titulo">
                <div class="form-text">Por exemplo: Programador JavaScript e VueJS.</div>
            </div>
        </div>

        <div class="row mt-3">
            <div class="col">
                <label class="form-label">Descrição</label>
                <textarea type="text" class="form-control" v-model="descricao"></textarea>
                <div class="form-text">Informe os detalhes da vaga.</div>
            </div>
        </div>

        <div class="row mt-3">
            <div class="col">
                <label class="form-label">Salário</label>
                <input type="number" class="form-control" v-model="salario">
                <div class="form-text">Informe o salário.</div>
            </div>

            <div class="col">
                <label class="form-label">Modalidade</label>
                <select class="form-select" v-model="modalidade">
                    <option value="" disabled>--Selecione</option>
                    <option value="1">Home Office</option>
                    <option value="2">Presencial</option>
                </select>
                <div class="form-text">Informe onde as atividades serão realizadas.</div>
            </div>

            <div class="col">
                <label class="form-label">Tipo</label>
                <select class="form-select" v-model="tipo">
                    <option value="" disabled>Selecione</option>
                    <option value="1">CLT</option>
                    <option value="2">PJ</option>
                </select>
                <div class="form-text">Informe o tipo de contratação.</div>
            </div>
        </div>

        <div class="row mt-3">
            <div class="col">
                <button type="submit" class="btn btn-primary" @click="salvarVaga()">Cadastrar</button>
            </div>
        </div>

    </div>
</template>
<script>
export default {
    name: 'PublicarVaga',
    data: () => ({
        titulo: '',
        descricao: '',
        salario: '',
        modalidade: '',
        tipo: '',
        publicacao: ''
    }),
    methods: {
        salvarVaga() {
            let vagas = JSON.parse(localStorage.getItem('vagas'));

            if (!vagas) {
                vagas = [];
            }
            vagas.push({
                titulo: this.titulo,
                descricao: this.descricao,
                salario: this.salario,
                modalidade: this.modalidade,
                tipo: this.tipo,
                publicacao: (new Date()).toLocaleDateString("pt-BR"),
            });
            // localStorage é nativo do javascript
            // precisa converter o valor de vaga usando o stringfy pq se não, o que o localstorage
            // recebe é só uma descrição do objeto. pq o que ele espera é uma string
            localStorage.setItem('vagas', JSON.stringify(vagas));
        }
    }
}
</script>

<style></style>
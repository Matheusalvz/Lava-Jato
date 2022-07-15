<template>
    <div>
        <div>
            <form id="car-form" @submit="createSolicitacao">
                <div class="input-container">
                    <label for="nome">Nome do cliente:</label>
                    <input type="text" name="nome" id="nome" v-model="nome" placeholder="Nome completo">
                </div>
                <div class="input-container">
                    <label for="marca">Marca do veículo</label>
                    <select name="marca" id="marca" v-model="marca">
                        <option value="">Selecione...</option>
                        <option v-for="marca in marcas" :key="marca.id" :value="marca.tipo">{{ marca.tipo }}</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="modelo">Modelo do veículo</label>
                    <select name="modelo" id="modelo" v-model="modelo">
                        <option value="">Selecione...</option>
                        <option v-for="modelo in modelos" :key="modelo.id" :value="modelo.tipo">{{ modelo.tipo }}</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="placa">Placa do veículo</label>
                    <input type="text" name="placa" id="placa" v-model="placa" placeholder="Placa">
                </div>
                <div class="input-container" id="opcionais-container">
                    <label for="opcionais" id="opcionais-title">Selecione os opcionais de lavagem</label>
                    <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
                        <input type="checkbox" name="opcionais" v-model="opcionais" :value="opcional.tipo">
                        <span>{{ opcional.tipo}}</span>
                    </div>
                </div> 
                <div class="input-container">
                    <input type="submit" class="submit-btn" value="Solicitar lavagem">
                </div>
            </form>
        </div>
    </div>
</template>

<script>

export default {
    name: "CarForm",
    data() {
        return {
            marcas: null,
            modelos: null,
            opcionaisdata: null,
            marca: null,
            modelo: null,
            opcionais: [],
            status: "Solicitado",
            msg: null
        }
    },
    methods: {
        async getVeiculos() {
            const req = await fetch("http://localhost:3000/veiculos");
            const data = await req.json();

            this.marcas = data.marcas;
            this.modelos = data.modelos;
            this.opcionaisdata = data.opcionais;
        },
        async createSolicitacao(e) {
        
        e.preventDefault();

        const data = { //Capta os dados inseridos no formulário
            nome: this.nome,
            marca: this.marca,
            modelo: this.modelo,
            placa: this.placa,
            opcionais: Array.from(this.opcionais),
            status: "Solicitado"
            }
        
        const dataJson = JSON.stringify(data); //Tranforma as informações em JSON

        const req = await fetch("http://localhost:3000/atendimentos",{
            method: "POST" ,
            headers: { "Content-Type": "application/json"} ,
            body: dataJson
        });

        const res = await req.json();

        console.log(res);
        }
    },
    mounted() {
        this.getVeiculos();
    }
}
</script>

<style scoped>
    #car-form{
        max-width: 400px;
        margin: 0 auto; /*Centralizar o formulário na tela*/
    }

    .input-container{
        display: flex;
        flex-direction: column; /*Label fica em uma linha e a coluna em outra*/
        margin-bottom: 20px;
    }

    label{ 
        font-weight: bold;
        margin-bottom: 15px; /*Separa a label do input*/
        color: #222;
        padding: 5px 10px;
        border-left: 4px solid #0d6edd; 
    }

    input, select {
        padding: 5px 10px; 
        width: 300px;
    }

    #opcionais-container { 
        flex-direction: row;
        flex-wrap: wrap;
    }

    #opcionais-title {
        width: 100%;
    }

    .checkbox-container {
        display: flex;
        align-items: flex-start; /*Alinha os itens no inicio*/
        width: 50%;
        margin-bottom: 20px;
    }
    .checkbox-container span,
    .checkbox-container input {
        width: auto;
    }
    .checkbox-container span {
        margin-left: 6px;
        font-weight: bold;
    }

    .submit-btn {
        background-color: #222;
        color: #418adf;
        font-weight: bold;
        border: 2px solid #222;
        padding: 10px;
        font-size: 16px;
        margin: 0 auto;
        cursor: pointer;
        transition: .5s;
    }
    .submit-btn:hover {
        background-color: transparent;
        color: #222;
    }
</style>
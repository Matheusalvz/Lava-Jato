<template>
    <div id="car-table">
        <div>
            <div id="car-table-heading">
                <div class="order-id">#:</div>
                <div>Cliente:</div>
                <div>Marca:</div>
                <div>Modelo:</div>
                <div>Placa:</div>
                <div>Opcionais:</div>
                <div>Ações:</div>
            </div>
        </div>
        <div id="car-table-rows">
            <div class="car-table-row" v-for="carro in carros" :key="carro.id">
                <div class="order-number">{{carro.id}}</div>
                <div>{{ carro.nome }}</div>
                <div>{{ carro.marca }}</div>
                <div>{{ carro.modelo }}</div>
                <div>{{ carro.placa }}</div>
                <div>
                    <ul>
                        <li v-for="(opcional, index) in carro.opcionais" :key="index"> {{ opcional }} </li>
                    </ul>
                </div>
                <select name="status" class="status">
                    <option value="">Selecione</option>
                    <option v-for="s in status" :key="s.id" :value="s.tipo" :selected="carro.status == s.tipo">{{ s.tipo }}</option>
                </select>
                <button class="delete-btn">Cancelar</button>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "Dashboard",
    data() {
        return { 
            carro: null,
            carros: null,
            carros_id: null,
            status: []
        }
    },
    methods: {
        async getAtendimentos() {
            const req = await fetch("http://localhost:3000/atendimentos");

            const data = await req.json();

            this.carros = data;

            //resgatar os status
            this.getStatus();
        },

        async getStatus(){
            
        const req = await fetch("http://localhost:3000/status");

        const data = await req.json();

        this.status = data;
        

        }
    },
    mounted() {
        this.getAtendimentos();
    }
}

</script>

<style scoped>

    #car-table{
        max-width: 1200px;
        margin: 0 auto;
    }

    #car-table-heading,
    #car-table-rows,
    .car-table-row {
        display: flex;
        flex-wrap: wrap;
    }

    #car-table-heading {
        font-weight: bold;
        padding: 12px;
        border-bottom: 3px solid #333;
    }
    .car-table-row {
        width: 100%;
        padding: 12px;
        border-bottom: 1px solid #CCC;
    }
    #car-table-heading div,
    .car-table-row div {
        width: 12%;
    }

    #car-table-heading .order-id,
    .car-table-row .order-number {
        width: 5%;
    }

    select {
        padding: 12px 6px;
        margin-right: 12px;
    }
    .delete-btn {
        background-color: #222;
        color:#418adf;
        font-weight: bold;
        border: 2px solid #222;
        padding: 10px;
        font-size: 16px;
        margin: 0 auto;
        cursor: pointer;
        transition: .5s;
    }
    
    .delete-btn:hover {
        background-color: transparent;
        color: #222;
    }

    .status{
        height: 40px;
    }

    @media (max-width: 400px) {
        
        /* Responsividade */
    }
</style>

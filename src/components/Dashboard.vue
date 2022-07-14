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
            <div class="car-table-row">
                <div class="order-number">1</div>
                <div>Jonas</div>
                <div>GM</div>
                <div>Celta</div>
                <div>Placa</div>
                <div>
                    <ul>
                        <li>Vitrificação</li>
                        <li>Polimento</li>
                    </ul>
                </div>
                <select name="" id="">
                    <option value="">Selecione o status do serviço</option>
                </select>
                <button class="delete-btn">Cancelar Serviço</button>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "Dashboard"
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
        width: 19%;
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
</style>

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

</style>

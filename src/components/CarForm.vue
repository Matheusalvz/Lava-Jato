<template>
    <div>
        <div>
            <form id="car-form">
                <div class="input-container">
                    <label for="nome">Nome do cliente:</label>
                    <input type="text" name="nome" id="nome" v-model="nome" placeholder="Nome completo">
                </div>
                <div class="input-container">
                    <label for="nome">Marca e modelo do veículo</label>
                    <input type="text" name="nome" id="nome" v-model="nome" placeholder="Marca">
                </div>
                <div class="input-container">
                    <label for="nome">Placa do veículo</label>
                    <input type="text" name="placa" id="placa" v-model="nome" placeholder="Placa">
                </div>
                <div class="input-container">
                    <label for="nome">Selecione os opcionais de lavagem</label>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="motor">
                        <span>Lavagem do motor</span>
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="interna">
                        <span>Higienização Interna</span>
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="polimento">
                        <span>Polimento</span>
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="vitrificacao">
                        <span>Vitrificação de pintura</span>
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
    name: "CarForm"
}
</script>

<style scoped>
    
</style>
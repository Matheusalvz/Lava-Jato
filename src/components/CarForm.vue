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
                <div class="input-container" id="opcionais-container">
                    <label for="nome" id="opcionais-title">Selecione os opcionais de lavagem</label>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="motor">
                        <span>Lavagem do motor</span>
                    </div>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="interna">
                        <span>Higienização Interna</span>
                    </div>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="polimento">
                        <span>Polimento</span>
                    </div>
                    <div class="checkbox-container">
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
    #burger-form{
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
<script setup>
import { cep, estado, cidade, bairro, rua, numero } from '@/stores/enderecoStore'
const emit = defineEmits(['submit'])

const estados = [
    'AC', 'AL', 'AP', 'AM', 'BA', 'CE', 'DF', 'ES', 'GO',
    'MA', 'MT', 'MS', 'MG', 'PA', 'PB', 'PR', 'PE', 'PI',
    'RJ', 'RN', 'RS', 'RO', 'RR', 'SC', 'SP', 'SE', 'TO'
]

const buscarCep = async () => {
    const cepLimpo = cep.value.replace(/\D/g, '')
    if (cepLimpo.length !== 8) return

    try {
        const response = await fetch(`https://viacep.com.br/ws/${cepLimpo}/json/`)
        const data = await response.json()
        if (data.erro) return

        estado.value = data.uf
        cidade.value = data.localidade
        bairro.value = data.bairro
        rua.value = data.logradouro
    } catch (error) {
        console.error('Erro ao buscar o CEP:', error)
    }
}
</script>

<template>
    <section class="containerLogin">
        <div>
            <h3>Insira seu Endereço</h3>
            <form @submit.prevent>
                <section class="columns">
                    <fieldset>
                        <label for="cep">CEP</label>
                        <input type="text" v-model="cep" @blur="buscarCep" placeholder="Insira seu CEP" maxlength="8"
                            minlength="8" required />
                    </fieldset>
                    <fieldset>
                        <label for="estado">Estado</label>
                        <select v-model="estado" :disabled="!cep">
                            <option disabled value="">Selecionar</option>
                            <option v-for="uf in estados" :key="uf" :value="uf">{{ uf }}</option>
                        </select>
                    </fieldset>
                </section>

                <section class="columns">
                    <fieldset>
                        <label for="cidade">Cidade</label>
                        <input type="text" v-model="cidade" placeholder="Insira a cidade" :disabled="!cep" />
                    </fieldset>
                    <fieldset>
                        <label for="bairro">Bairro</label>
                        <input type="text" v-model="bairro" placeholder="Insira o bairro" :disabled="!cep" />
                    </fieldset>
                </section>

                <section class="column">
                    <fieldset class="rua">
                        <label for="rua">Rua</label>
                        <input type="text" v-model="rua" placeholder="Insira sua rua" :disabled="!cep" />
                    </fieldset>
                    <fieldset class="numeroCasa">
                        <label for="numero">Número</label>
                        <input type="number" v-model="numero" placeholder="Insira o número" :disabled="!cep" />
                    </fieldset>
                </section>

                <button type="button" @click="emit('submit')">
                    ENTRAR
                </button>
            </form>
        </div>
    </section>
</template>

<style scoped>
.containerLogin {
    background-color: #DEDEDE82;
    width: 100%;
    border-radius: 20px;
}

.containerLogin>div {
    padding: 20px 20px 40px 30px;
}

h3 {
    color: #085118;
    font-family: "poppies", sans-serif;
    font-weight: 500;
    font-size: calc(24px - 0.5vh);
    line-height: 100%;
    letter-spacing: 0%;
    margin: 20px 0 30px 0;
}

label {
    font-family: "Poppins", sans-serif;
    font-weight: 600;
    font-size: calc(16px - 0.5vh);
    line-height: 100%;
    letter-spacing: 0%;
    margin: 5px 7px;
}

input,
select {
    border: 1px solid black;
    border-radius: 10px;
    padding: 5px;
    margin-bottom: 50px;
}

input::placeholder {
    color: #B5B5B5;
}

.column {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.column fieldset.rua {
    min-width: 60% !important;
}

.column .numeroCasa {
    min-width: 20% !important;
}

fieldset {
    border: 0;
    display: flex;
    flex-direction: column;
    height: 70px;
}

.columns {
    display: flex;
    justify-content: space-between;
}

.columns>fieldset {
    width: 50%;
}

button {
    border: 1px solid #74D954;
    border-radius: 8px;
    background-color: #0E8228E5;
    padding: 10px;
    font-family: "proza libre", sans-serif;
    color: #fff;
    font-size: calc(22px - 0.5vh);
    width: 100%;
}
</style>

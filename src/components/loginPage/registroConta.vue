<script setup>
import { computed } from 'vue'
const props = defineProps(['modelValue'])
const emit = defineEmits(['update:modelValue'])
const model = computed({
    get: () => props.modelValue,
    set: (valor) => emit('update:modelValue', valor)
})
</script>

<template>
    <section class="containerLogin">
        <div>
            <h3>Criar conta</h3>
            <form @submit.prevent>
                <fieldset>
                    <label for="nome">Nome</label>
                    <input v-model="model.nome" type="text" placeholder="Digite seu Nome" required />
                </fieldset>
                <fieldset>
                    <label for="telefone">Celular</label>
                    <input v-model="model.telefone" type="tel" placeholder="Digite seu celular" required />
                </fieldset>
                <fieldset>
                    <label for="email">E-mail</label>
                    <input v-model="model.email" type="email" placeholder="Digite seu email" required />
                </fieldset>
                <fieldset>
                    <label for="cpf">CPF</label>
                    <input v-model="model.cpf" type="text" placeholder="Digite seu CPF" required />
                </fieldset>
                <section class="senha">
                    <fieldset class="column">
                        <label for="senha">Senha</label>
                        <input v-model="model.senha" type="password" placeholder="Digite sua senha" required />
                    </fieldset>
                    <fieldset class="column">
                        <label for="confirmarSenha">Confirmar Senha</label>
                        <input v-model="model.confirmarSenha" type="password" placeholder="Confirme sua senha" required />
                    </fieldset>
                </section>
            </form>
        </div>
    </section>
</template>

<style scoped>
.containerLogin {
    background-color: #dedede82;
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

input {
    border: 1px solid black;
    border-radius: 10px;
    padding: 5px;
    margin-bottom: 50px;
}

input::placeholder {
    color: #b5b5b5;
}

.column {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

fieldset {
    border: 0;
    display: flex;
    flex-direction: column;
    height: 70px;
}

.senha {
    display: flex;
    justify-content: space-between;
    flex-direction: row;
    gap: 20px;
}

button {
    border: 1px solid #74d954;
    border-radius: 8px;
    background-color: #0e8228e5;
    padding: 10px;
    font-family: "proza libre", sans-serif;
    color: #fff;
    font-size: calc(20px - 0.5vh);
    cursor: pointer;
}
</style>

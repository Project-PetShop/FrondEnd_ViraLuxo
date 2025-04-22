<script setup>
import { ref } from 'vue'
import { validarCPF } from '../utils/validaCPF'
import loginNav from '@/components/loginPage/loginNav.vue'
import registroConta from '@/components/loginPage/registroConta.vue'
import registroEndereco from '@/components/loginPage/registroEndereco.vue'
import { cep, estado, cidade, bairro, rua, numero } from '../stores/enderecoStore'

const conta = ref({
    nome: '',
    telefone: '',
    email: '',
    cpf: '',
    senha: '',
    confirmarSenha: ''
})

import * as enderecoData from '@/stores/enderecoStore'

const handleCadastro = () => {
    if (conta.value.senha !== conta.value.confirmarSenha) {
        alert('As senhas não coincidem')
        return
    } else if (!conta.value.nome || !conta.value.telefone || !conta.value.email || !conta.value.cpf || !conta.value.senha) {
        alert('Preencha todos os campos')
        return
    } else if (!validarCPF(conta.value.cpf)) {
        alert('CPF inválido!')
        return
    }


    const dadosCompletos = {
        ...conta.value,
        ...Object.fromEntries(
            Object.entries(enderecoData).map(([key, refVal]) => [key, refVal.value])
        )
    }
    console.log('Dados para cadastro:', dadosCompletos)
    //router.push("/")

    conta.value({
        nome: '',
        telefone: '',
        email: '',
        cpf: '',
        senha: '',
        confirmarSenha: ''
    })
    for (const key in enderecoData) {
        if (enderecoData[key]?.value !== undefined) {
            enderecoData[key].value = ''
        }
    }
}
</script>


<template>
    <loginNav />
    <div class="container">
        <h2>Acessar ou criar conta</h2>


        <section id="makeLogin">
            <registroConta v-model="conta" />
        </section>


        <section id="makeAccount">
            <registroEndereco @submit="handleCadastro" />
        </section>
    </div>


    <section class="imgPatas"></section>
</template>


<style scoped>
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    top: 221px;
    padding: 0 calc(320px - 4vw);
    column-gap: 90px;
}


#makeLogin {
    width: 100%;
    grid-column: 1;
}


h2 {
    font-family: 'Poppins', sans-serif;
    color: #085118;
    font-weight: 600;
    font-size: calc(28px - 0.5vh);
    line-height: 100%;
    letter-spacing: 0%;
    margin-top: 40px;
    text-align: center;
    justify-content: center;
    height: 24px;
    display: flex;
}


.imgPatas {
    background-image: url(/loginPage/patasFundo.png);
    width: calc(100% - 43px);
    height: 340px;
    bottom: 100px;
    position: relative;
    z-index: -1;
    padding: 0;
    left: 43px;
}
</style>

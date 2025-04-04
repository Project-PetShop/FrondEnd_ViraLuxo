<script setup></script>
<template>
    <div class="content">
        <h3>Criar uma conta é rápido, fácil e gratuito!</h3>
        <p>Com a sua conta da ViraLuxo você tem acesso a Ofertas exclusivas, descontos, pode pedir nossos serviços,
            acompanhar os seus pedidos e muito mais!</p>
        <button><router-link to="/register">CRIAR A MINHA CONTA</router-link></button>
    </div>
</template>
<style scoped>
.content {
    margin: 0;
    padding: 0;
}

h3 {
    color: #085118;
    font-family: "proza libre", sans-serif;
    font-weight: 500;
    font-size: calc(24px - 0.5vh);
    line-height: 100%;
    letter-spacing: 0%;
    margin: 20px 0 30px 0;
    max-width: 250px;
}

p {
    font-family: "proza libre", sans-serif;
    font-weight: 400;
    font-size: calc(18px - 0.5vh);
    line-height: 100%;
    letter-spacing: 0%;
    color: #000000CC;
    max-width: 350px;
}

button {
    border: 1px solid #74D954;
    border-radius: 8px;
    background-color: #0E8228E5;
    padding: 10px;
    font-family: "proza libre", sans-serif;
    color: #fff;
    width: 80%;
    font-size: calc(18px - 0.5vh);
    margin-top: 40px;
}
</style>

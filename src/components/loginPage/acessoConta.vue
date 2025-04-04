<script setup>
</script>
<template>
    <section class="containerLogin">
        <div>
            <h3>Acesse sua conta</h3>
            <form action="">
                <label for="name">E-mail ou CPF</label>
                <input type="text" placeholder="Digite seu e-mail ou CPF">
                <div class="flex">
                    <label for="password">Senha</label>
                    <p><router-link >Esqueci a senha</router-link></p>
                </div>
                <input type="password" name="password" placeholder="Digite sua senha">

                <button><router-link to="">ENTRAR</router-link></button>
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

form {
    display: flex;
    flex-direction: column;
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
    font-size: calc(18px - 0.5vh);
    line-height: 100%;
    letter-spacing: 0%;
    margin: 5px 7px;
}

input {
    border: 1px solid black;
    border-radius: 20px;
    padding: 10px;
    margin-bottom: 50px;
}

input::placeholder {
    color: #B5B5B5;
}

.flex {
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.flex p {
    margin: 0;
    color: blue;
    font-family: "Poppins", sans-serif;
    font-weight: 400;
    font-size: calc(12px - 0.5vh);
    line-height: 100%;
    letter-spacing: 0%;
    text-decoration: underline;
    text-decoration-style: solid;
    text-decoration-thickness: 0%;
    text-decoration-skip-ink: auto;
}
button{
    border: 1px solid #74D954;
    border-radius: 8px;
    background-color: #0E8228E5;
    padding: 10px;
    font-family: "proza libre", sans-serif;
    color: #fff;
    font-size: calc(22px - 0.5vh);
}
</style>
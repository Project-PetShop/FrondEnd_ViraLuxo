<script setup>
</script>
<template>
    <section class="containerLogin">
        <div>
            <h3>Crie sua conta</h3>
            <form action="">
                <fieldset>
                    <label for="name">Nome e Sobrenome</label>
                    <input type="text" placeholder="Digite seu Nome e Sobrenome">
                </fieldset>
                <fieldset>
                    <label for="telefone">Celular</label>
                    <input type="number" placeholder="DDD + Celular">
                </fieldset>
                <fieldset>
                    <label for="emal">E-mail</label>
                    <input type="email" placeholder="Digite seu e-mail">
                </fieldset>
                <fieldset>
                    <label for="cpf">CPF</label>
                    <input type="text" name="cpf" placeholder="Digite seu CPF">
                </fieldset>
                <section class="senha">
                    <div class="column">
                        <fieldset>
                            <label for="password">Senha</label>
                            <input type="password" name="password" placeholder="Digite sua senha">
                        </fieldset>

                        <div class="legendaSenha">
                            <p>Padrão de senha</p>
                            <ul>
                                <li>Mínimo 8 caracteres
                                </li>
                                <li>Letra Minúscula</li>
                            </ul>
                        </div>
                    </div>
                    <div class="column">
                        <fieldset>
                            <label for="password">Confirmar senha</label>
                            <input type="password" name="password" placeholder="Confirme sua senha">
                        </fieldset>
                        <div class="legendaSenha">
                            <ul>
                                <li>Letra Maiúscula
                                </li>
                                <li>Números
                                </li>
                            </ul>
                        </div>
                    </div>
                </section>
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
    font-size: calc(24px - 0.3vh);
    line-height: 100%;
    letter-spacing: 0%;
    margin: 20px 0 30px 0;
}

label {
    font-family: "Poppins", sans-serif;
    font-weight: 600;
    font-size: calc(16px - 0.3vh);
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
    color: #B5B5B5;
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
    height: 50px;
}

.senha {
    display: flex;
    justify-content: space-between;
    flex-direction: row;
}

.legendaSenha {
    line-height: 100%;
    letter-spacing: 0%;
    color: #000000E5;
    margin: 0 17px;
}

.legendaSenha p {
    margin: 0;
    padding: 0;
    font-family: "Proza Libre", sans-serif;
    font-weight: 600;
    font-size: calc(12px -  0.3vh);
}

.legendaSenha ul {
    margin: 0;
    padding: 0;
    display: inline;
    list-style-position: unset;
}

.legendaSenha ul li {
    margin-left: 17px;
    padding: 2px;
    font-family: "Proza Libre", sans-serif;
    font-weight: 400;
    font-size: calc(10px - 0.3vh);
    line-height: 100%;
    letter-spacing: 0%;
}
</style>
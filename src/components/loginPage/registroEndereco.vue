<script setup>
</script>
<template>
    <section class="containerLogin">
        <div>
            <h3>Insira seu Endereço</h3>
            <form action="">
                <section class="columns">
                    <fieldset>
                        <label for="cep">CEP</label>
                        <input type="number" placeholder="Insira seu CEP">
                    </fieldset>
                    <fieldset>
                        <label for="estado">Estado</label>
                        <select name="estado">
                            <option value="">Selecionar</option>
                        </select>
                    </fieldset>
                </section>
                <section class="columns">
                    <fieldset>
                        <label for="cidade">Cidade</label>
                        <input type="text" placeholder="Insira a cidade">
                    </fieldset>
                    <fieldset>
                        <label for="bairro">Bairro</label>
                        <input type="text" placeholder="Insira o bairro">
                    </fieldset>
                </section>
                <section class="column" >
                    <fieldset class="rua">
                        <label for="rua">Rua</label>
                        <input type="text" placeholder="Insira sua rua">
                    </fieldset>
                    <fieldset class="numeroCasa">
                        <label for="numero">N°</label>
                        <input type="number" placeholder="Insira o número">
                    </fieldset>
                </section>
                <button><router-link to="">FINALIZAR CADASTRO</router-link></button>
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
    min-width: 30% !important;
}

fieldset {
    border: 0;
    display: flex;
    flex-direction: column;
    height: 50px;
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
    font-size: calc(19px - 0.5vh);
    width: 100%;
    margin-top: 70px;
}
</style>
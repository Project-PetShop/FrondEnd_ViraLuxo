<script setup>
import loginNav from '@/components/loginPage/loginNav.vue'
import acessoConta from '@/components/loginPage/acessoConta.vue'
import sectionAcessoAlternativo from '@/components/loginPage/sectionAcessoAlternativo.vue';
</script>
<template>
    <loginNav />
    <div class="container">
        <h2>Acessar ou criar conta</h2>
        <div></div>

        <section id="makeLogin">

            <acessoConta />
        </section>
        <section id="makeAccount">
            <sectionAcessoAlternativo/>
        </section>
    </div>
    <section class="imgPatas">
    </section>
</template>
<style scoped>
.container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    top: 221px;
    padding: 0 calc(320px - 4vw);
    column-gap: 90px;
}

#makeLogin{
    width: 100%;
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
.imgPatas{
    background-image: url(/public/loginPage/patasFundo.png);
    width: 100%;
    height: 340px;
    bottom: 100px;
    position: relative;
    z-index: -1;
    padding: 0;
}


</style>

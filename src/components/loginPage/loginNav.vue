<script setup></script>
<template>
  <nav>
    <div class="logo">
      <img src="/logo.png" alt="logo" />
      <h2>ViraLuxo</h2>
    </div>
    <div class="login">
      <img src="/user.png" alt="user" />
      <div class="cadastro">
        <p><router-link to="">Entrar</router-link></p>
        <p id="cadastre"><router-link to="">Cadastre-se</router-link></p>
      </div>
    </div>
  </nav>
</template>
<style scoped>
nav {
  display: flex;
  width: 1920;
  height: 54px;
  top: 14px;
  justify-content: space-between;
  padding: 0 calc(300px - 4vw);
  border-bottom-width: 1.5px;
  border-bottom: 1px solid #00000080;
}
h2,
p {
  margin: 0;
  font-family: 'Poppins', sans-serif;
}
.logo {
  display: flex;
  margin-top: 10px;
}

.logo img {
  width: auto;
  height: 26px;
}

.logo h2 {
  font-size: calc(24px - 0.5vh);
  padding: 0;
  margin-top: 0;
  margin-left: 8px;
  font-weight: 700;
  letter-spacing: 0%;
}
.login {
  display: flex;
  margin-top: 10px;
}
.login img{
    width: 35px;
    height: 35px;
}
.cadastro p{
    padding-top: 0%;
    font-size: calc(17px - 0.5vh);
    font-weight: 500;
    letter-spacing: 0%;
}
#cadastre{
    font-size: calc(15px - 0.5vh);
}

a {
  text-decoration: none;
  color: black;
}
</style>

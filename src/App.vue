<template>
  <div id="titulo">
    <img src="./assets/logo.png" alt="">
    <h1>
      Textos padrões para abertura de
    </h1> 
    <h1>
      Incidentes nas Cicoms junto à PRODEB
    </h1> 
    <selectCicom />
    <inputTexto textoPadrao ="incidente" />
    <inputTexto textoPadrao ="Whatsapp" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import inputTexto from './components/inputText.vue';
import selectCicom from './components/selectCicom.vue';
import "bootstrap/dist/css/bootstrap.min.css"
import "bootstrap"


export default {
  name: 'App',
  components: {
    // HelloWorld
    inputTexto,
    selectCicom,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img {
  width: 35px;
  height: 35px;
}

</style>

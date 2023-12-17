<template>
  <vue-title title="Static Title"></vue-title>
  <div id="titulo">
    <h1>Texto Padrão para Promt ChatGPT</h1>
    <div class="campos">
      <h3>Área do Imovel</h3>
      <input type="number" v-model="dadosImovel.area">
    </div>
    <div class="campos">
      <h3>Área Construida</h3>
      <input type="number" v-model="dadosImovel.areaConstruida">
    </div>
    <div class="campos">
      <h3>Quartos</h3>
      <input type="number" v-model="dadosImovel.quartos">
    </div>
    <div class="campos">
      <h3>Suites</h3>
      <input type="number" v-model="dadosImovel.suites">
    </div>
    <button @click="gerarTextoFinal()">Gerar Texto</button>
    <br>
    <textarea name="" id="" cols="30" rows="10" v-model="textoFinal">  </textarea>
    
    
    <footer>
      Desenvolvido por 
      <a href="https://linktr.ee/peter.lolivera" target="_blank" class="link">
        <b class="author">PETER LANGE</b>
      </a> 
      em <b>VUE.JS</b> <img src="./assets/logo.png" alt="" />
    </footer>
  </div>
  
</template>

<script>

import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";

export default {
  
  name: "App",
  created(){
    // muda o titulo da aba do navegador
    document.title = "Texto para ChatGPT"
    },
  data() {
    return {
      dadosImovel: {
          area: 0,
          areaConstruida: 0,
          quartos: 0,
          suites: 0,
        },
      textoFinal: ''
    };
  },
  components: {
    
  },
  methods: {
    gerarTextoFinal() {
      this.textoFinal = `Gere texto para o anuncio de um ímovel com ${this.dadosImovel.area} de área total, ${this.dadosImovel.areaConstruida} de área Construida, ${this.dadosImovel.quartos} quartos, ${this.dadosImovel.suites} suites. O texto deve ter mais de 1500 caracteres.`
    }
    
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
img {
  width: 25px;
  height: 25px;
}

.author{
  color: #41b883;
}
footer {
  text-align: center;
  width: 500x;
}
.link {
  text-decoration: none;
}

.campos{
  display: flex;
  justify-content: center;
}

</style>

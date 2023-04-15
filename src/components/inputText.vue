<template>
  <div class="texts-area">
    <textarea
      textoGerado
      class="textsGenerated"
      :placeholder="textoInserido"
      :value="textoFinal"
      :id="textoPadrao"
    ></textarea>
    <button class="buttons" @click="copiarTexto()">📋</button>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";
export default {
  name: "inputTexto",
  props: ["textoPadrao", 'textoRecebido'],
  data() {
    return {
      textoFinal: this.textoRecebido,
      textoInserido: `Texto para o ${this.textoPadrao}\nClique no botão ao lado para copiar para a área de transferência!`,
    };
  },
  methods: {
    copiarTexto: function () {
      const textoGerado = document.getElementById(this.textoPadrao)
      navigator.clipboard.writeText(textoGerado.value)
    },
  },
};
</script>

<style>
.texts-area {
  display: flex;
  justify-content: center;
  margin-bottom: 30px;
}
.textsGenerated,
.buttons {
  border: 1px solid gray;
}

.buttons:hover {
  background-color: aquamarine;
}

.textsGenerated {
  border-radius: 5px 0 0 5px;
  width: 1000px;
  resize: none;
  border: 1px solid gray;
  border-right: 0px;
  height: 150px;
}

.buttons {
  background-color: rgb(218, 218, 218);
  border-radius: 0 5px 5px 0;
  font-size: 20px;
}
</style>

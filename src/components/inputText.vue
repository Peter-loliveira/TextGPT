<template>
  <div class="texts-area">
    <textarea
      class="textsGenerated"
      :placeholder="textoInserido"
      :id="idTextArea"
      :value="exibeTexto"
    ></textarea>
    <button class="buttons" @click="copiarTexto()"> 📋 </button>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";
export default {
  name: "inputTexto",
  props: ["idTextArea", "textoRecebido"],
  data() {
    return {
      textoFinal: "",
      textoInserido: `Texto para o ${this.idTextArea}\nClique no botão ao lado para copiar para a área de transferência!`,
    };
  },
  methods: {
    copiarTexto: function () {
      const textoGerado = document.getElementById(this.idTextArea)
      navigator.clipboard.writeText(textoGerado.value)
    },
      
  },
  computed: {
    exibeTexto() {
      return this.textoRecebido
    }
  }
};
</script>

<style>
.texts-area {
  display: flex;
  justify-content: center;
  margin-bottom: 10px;
}
.textsGenerated,
.buttons {
  border: 1px solid gray;
  padding: 10px;
}

.buttons:hover {
  background-color: aquamarine;
}

.textsGenerated {
  border-radius: 5px 0 0 5px;
  width: 1000px;
  height: 200px;
  resize: none;
  border: 1px solid gray;
  border-right: 0px;
  
}

.buttons {
  background-color: rgb(218, 218, 218);
  border-radius: 0 5px 5px 0;
  font-size: 20px;
}
</style>

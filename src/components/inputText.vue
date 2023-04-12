<template>
  <div class="texts-area">
    <textarea class="textsGenerated" :placeholder="textoInserido"></textarea>
    <button class="buttons">📋</button>
  </div>
</template>

<script>
export default {
  name: "inputTexto",
  props: ["textoPadrao"],
  data() {
    return {
      textoInserido: `${this.textoPadrao}\nClique no botão ao lado para copiar para a área de transferência!`,
    };
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
  background-color: aquamarine;
  border-radius: 0 5px 5px 0;
  font-size: 20px;
}
</style>

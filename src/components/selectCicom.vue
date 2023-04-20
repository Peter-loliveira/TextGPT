<template>
  <div id="lista">
    <select
      class="form-select form-select-lg p-4"
      id="lista-cicoms"
      @change="this.preencherCamposTexto()"
    >
      <option>Selecione uma Cicom</option>
      <option
        v-for="cicom in cicoms"
        :key="cicom.circuito"
      >
      {{ cicom.cicom.toUpperCase() }} - {{ cicom.circuito }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "selectCicom",
  props: ['cicoms'],
  methods: {
    preencherCamposTexto() {
    const select = document.getElementById('lista-cicoms').selectedIndex
    console.log(select);
    if (select === 0 ){
      this.$emit('zerarTextos')
      return
    } else {
      this.$emit('preencher')
    }
    
    }
  },
};
</script>

<style scoped>
#lista-cicoms {
  width: 1046px;
}
#lista {
  display: flex;
  flex: row;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}
#first-item {
  color: red;
}
select {
  border: 1px solid rgb(153, 153, 153);
}
</style>

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
      {{ cicom.cicom.toUpperCase() }} -{{ cicom.circuito }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "selectCicom",
  props: ['cicoms'],
  data() {
    return {
       // Lista de CICOMS e seus dados para a bertura do chamado
      // cicoms: [
      //   {
      //     cicom: "Alagoinhas",
      //     circuito: "ALGRG0028I",
      //     RG: "4",
      //     Tel: "(75)3423-9200",
      //   },
      //   {
      //     cicom: "Barreiras",
      //     circuito: "BRSRG0027I",
      //     RG: "4",
      //     Tel: "(77)3611-0190",
      //   },
      //   {
      //     cicom: "Brumado",
      //     circuito: "BMDRG0010I",
      //     RG: "4",
      //     Tel: "(77)3453-2649",
      //   },
      //   {
      //     cicom: "Esplanada",
      //     circuito: "ESPRG0006I",
      //     RG: "4",
      //     Tel: "(75)3413-7600",
      //   },
      //   {
      //     cicom: "Euclides da Cunha",
      //     circuito: "ECNRG0010I",
      //     RG: "4",
      //     Tel: "(75)32710190",
      //   },
      //   {
      //     cicom: "Feira de Santana",
      //     circuito: "FRSRG0074I",
      //     RG: "4",
      //     Tel: "(75)3224-0918",
      //   },
      //   {
      //     cicom: "Guanambi",
      //     circuito: "GMBRG0014I",
      //     RG: "4",
      //     Tel: "(77)3451-5399",
      //   },
      //   {
      //     cicom: "Ibotirama",
      //     circuito: "ITMRG0006I",
      //     RG: "4",
      //     Tel: "(77)3698-6500",
      //   },
      //   {
      //     cicom: "Irecê",
      //     circuito: "IRCRG0019I",
      //     RG: "4",
      //     Tel: "(74)3641-5935",
      //   },
      //   {
      //     cicom: "Itaberaba",
      //     circuito: "ITRRG0018I",
      //     RG: "4",
      //     Tel: "(75)3251-8450",
      //   },
      //   {
      //     cicom: "Itabuna",
      //     circuito: "ITBRG0036I",
      //     RG: "4",
      //     Tel: "(73)32141500",
      //   },
      //   {
      //     cicom: "Jequié",
      //     circuito: "JQERG0035I",
      //     RG: "4",
      //     Tel: "(73)3528-3900",
      //   },
      //   {
      //     cicom: "Juazeiro",
      //     circuito: "JUARG0041I",
      //     RG: "4",
      //     Tel: "(74)3611-9230",
      //   },
      //   {
      //     cicom: "Paulo Afonso",
      //     circuito: "PAFRG0023I",
      //     RG: "4",
      //     Tel: "(75)3281-8900",
      //   },
      //   {
      //     cicom: "Porto Seguro",
      //     circuito: "PSGRG0020I",
      //     RG: "4",
      //     Tel: "(73)3268-9330",
      //   },
      //   {
      //     cicom: "Santa Maria da Vitoria",
      //     circuito: "SMVRG0014I",
      //     RG: "4",
      //     Tel: "(77)3483-6549",
      //   },
      //   {
      //     cicom: "Santo Antônio de Jesus",
      //     circuito: "SAJRG0016I",
      //     RG: "4",
      //     Tel: "(75)3631-8450",
      //   },
      //   {
      //     cicom: "Senhor do Bonfim",
      //     circuito: "SDBRG0018I",
      //     RG: "4",
      //     Tel: "(74)3541-3995",
      //   },
      //   {
      //     cicom: "Serrinha",
      //     circuito: "SRRRG0019I",
      //     RG: "4",
      //     Tel: "(75) 3261-8247",
      //   },
      //   {
      //     cicom: "Teixeira de Freitas",
      //     circuito: "TXFRG0020I",
      //     RG: "4",
      //     Tel: "(73)3165-2199",
      //   },
      //   {
      //     cicom: "Valença",
      //     circuito: "VLCRG0018I",
      //     RG: "4",
      //     Tel: "(75)36433400",
      //   },
      //   {
      //     cicom: "Vitoria da Conquista",
      //     circuito: "VCARG0038I",
      //     RG: "4",
      //     Tel: "(77) 3420-8800",
      //   },
      // ],
     
    };
  },
  methods: {
    // gerarTexto: function () {
    //   const lista = document.getElementById("lista-cicoms");
    //   this.indexCicomSelecionada = lista.selectedIndex - 1;
    //   this.geraHora()
    //   this.textoFinal = `CICOM ${this.cicoms[this.indexCicomSelecionada].cicom.toUpperCase()}.\nInformamos que às ${this.dataIncidente} foi constatado que o link de dados do CICOM na cidade de ${this.cicoms[this.indexCicomSelecionada].cicom.toUpperCase()}, do circuito ${this.cicoms[this.indexCicomSelecionada].circuito.toUpperCase()}, encontra-se inoperante. \nInformamos ainda que o atendimento é de emergência operando 24h e não pode parar.\nTelefone / Contato: ${this.cicoms[this.indexCicomSelecionada].Tel} / Coordenador ou Adjunto da CICOM.\nChamado aberto por `;
    //   this.whatsappFinal = `Foi aberto um Incidente junto à PRODEB referente à queda do link de DADOS da CICOM ${this.cicoms[this.indexCicomSelecionada].cicom.toUpperCase()}.\nIncidente Nº: `;
    //   this.preencherCamposTexto()
      
    // },
    // geraHora: function() {
    //   let data = new Date();
    //   let dia = data.getDate();
    //   if (dia < 10) {
    //     dia = "0" + dia;
    //   }

    //   let mes = data.getMonth() + 1;
    //   if (mes < 10) {
    //     mes = "0" + mes;
    //   }

    //   let ano = data.getFullYear();

    //   let hora = data.getHours();
    //   if (hora < 10) {
    //     hora = "0" + hora;
    //   }

    //   let min = data.getMinutes();
    //   if (min < 10) {
    //     min = "0" + min;
    //   }
    //   this.dataIncidente =  `${hora}h${min} do dia ${dia}/${mes}/${ano}`
    // },
    preencherCamposTexto: function() {
      this.$emit('preencher')
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

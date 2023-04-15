<template>
  <div id="titulo">
    <img src="./assets/logo.png" alt="" />
    <h1>Textos padrões para abertura de</h1>
    <h1>Incidentes nas Cicoms junto à PRODEB</h1>
    <selectCicom @preencher="preencherCampos()" :cicoms="cicoms" />
    <inputTexto :textoPadrao="incidente" :textoRecebido="textoInciente" />
    <inputTexto :textoPadrao="whatsapp" :textoRecebido="textoWhatsapp" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import inputTexto from "./components/inputText.vue";
import selectCicom from "./components/selectCicom.vue";
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";

export default {
  name: "App",
  data() {
    return {
      dataIncidente: "",

      incidente: 'incidente',
      whatsapp: 'whatsapp',

      textoInciente: "",
      textoWhatsapp: "",
      cicoms: [
        {
          cicom: "Alagoinhas",
          circuito: "ALGRG0028I",
          RG: "4",
          Tel: "(75)3423-9200",
        },
        {
          cicom: "Barreiras",
          circuito: "BRSRG0027I",
          RG: "4",
          Tel: "(77)3611-0190",
        },
        {
          cicom: "Brumado",
          circuito: "BMDRG0010I",
          RG: "4",
          Tel: "(77)3453-2649",
        },
        {
          cicom: "Esplanada",
          circuito: "ESPRG0006I",
          RG: "4",
          Tel: "(75)3413-7600",
        },
        {
          cicom: "Euclides da Cunha",
          circuito: "ECNRG0010I",
          RG: "4",
          Tel: "(75)32710190",
        },
        {
          cicom: "Feira de Santana",
          circuito: "FRSRG0074I",
          RG: "4",
          Tel: "(75)3224-0918",
        },
        {
          cicom: "Guanambi",
          circuito: "GMBRG0014I",
          RG: "4",
          Tel: "(77)3451-5399",
        },
        {
          cicom: "Ibotirama",
          circuito: "ITMRG0006I",
          RG: "4",
          Tel: "(77)3698-6500",
        },
        {
          cicom: "Irecê",
          circuito: "IRCRG0019I",
          RG: "4",
          Tel: "(74)3641-5935",
        },
        {
          cicom: "Itaberaba",
          circuito: "ITRRG0018I",
          RG: "4",
          Tel: "(75)3251-8450",
        },
        {
          cicom: "Itabuna",
          circuito: "ITBRG0036I",
          RG: "4",
          Tel: "(73)32141500",
        },
        {
          cicom: "Jequié",
          circuito: "JQERG0035I",
          RG: "4",
          Tel: "(73)3528-3900",
        },
        {
          cicom: "Juazeiro",
          circuito: "JUARG0041I",
          RG: "4",
          Tel: "(74)3611-9230",
        },
        {
          cicom: "Paulo Afonso",
          circuito: "PAFRG0023I",
          RG: "4",
          Tel: "(75)3281-8900",
        },
        {
          cicom: "Porto Seguro",
          circuito: "PSGRG0020I",
          RG: "4",
          Tel: "(73)3268-9330",
        },
        {
          cicom: "Santa Maria da Vitoria",
          circuito: "SMVRG0014I",
          RG: "4",
          Tel: "(77)3483-6549",
        },
        {
          cicom: "Santo Antônio de Jesus",
          circuito: "SAJRG0016I",
          RG: "4",
          Tel: "(75)3631-8450",
        },
        {
          cicom: "Senhor do Bonfim",
          circuito: "SDBRG0018I",
          RG: "4",
          Tel: "(74)3541-3995",
        },
        {
          cicom: "Serrinha",
          circuito: "SRRRG0019I",
          RG: "4",
          Tel: "(75) 3261-8247",
        },
        {
          cicom: "Teixeira de Freitas",
          circuito: "TXFRG0020I",
          RG: "4",
          Tel: "(73)3165-2199",
        },
        {
          cicom: "Valença",
          circuito: "VLCRG0018I",
          RG: "4",
          Tel: "(75)36433400",
        },
        {
          cicom: "Vitoria da Conquista",
          circuito: "VCARG0038I",
          RG: "4",
          Tel: "(77) 3420-8800",
        },
      ],
    };
  },
  components: {
    inputTexto,
    selectCicom,
  },
  methods: {
    preencherCampos: function () {
      this.geraHora();
      let indiceCicom =
        document.getElementById("lista-cicoms").selectedIndex - 1;

      this.textoWhatsapp = `Foi aberto um Incidente junto à PRODEB referente à queda do link de DADOS da CICOM ${this.cicoms[
        indiceCicom
      ].cicom.toUpperCase()}.\nIncidente Nº: `;

      // this.textoFinal = `CICOM ${this.cicoms[indexCicomSelecionada].cicom.toUpperCase()}.\nInformamos que às ${this.dataIncidente} foi constatado que o link de dados do CICOM na cidade de ${this.cicoms[this.cicomSelecionada].cicom.toUpperCase()}, do circuito ${this.cicoms[indexCicomSelecionada].circuito.toUpperCase()}, encontra-se inoperante. \nInformamos ainda que o atendimento é de emergência operando 24h e não pode parar.\nTelefone / Contato: ${this.cicoms[indexCicomSelecionada].Tel} / Coordenador ou Adjunto da CICOM.\nChamado aberto por `;
    },
    geraHora: function () {
      let data = new Date();
      let dia = data.getDate();
      if (dia < 10) {
        dia = "0" + dia;
      }

      let mes = data.getMonth() + 1;
      if (mes < 10) {
        mes = "0" + mes;
      }

      let ano = data.getFullYear();

      let hora = data.getHours();
      if (hora < 10) {
        hora = "0" + hora;
      }

      let min = data.getMinutes();
      if (min < 10) {
        min = "0" + min;
      }
      this.dataIncidente = `${hora}h${min} do dia ${dia}/${mes}/${ano}`;
    },
  },
  watch: {
    textoWhatsapp(){
      
    }
  }
};
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

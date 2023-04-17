<template>
  <vue-title title="Static Title"></vue-title>
  <div id="titulo">
    <h1>Textos padrões para Incidentes PRODEB</h1>
    <selectCicom @preencher="preencherCampos()" :cicoms="cicoms" />
    <inputTexto idTextArea="incidente" :textoRecebido="textoInciente" />
    <inputTexto idTextArea="whatsapp" :textoRecebido="textoWhatsapp" />
    <footer>
      Desenvolvido por 
      <a href="https://github.com/peter-loliveira" target="_blank" class="link">
        <b class="author">PETER LANGE</b>
      </a> 
      em <b>VUE.JS</b> <img src="./assets/logo.png" alt="" />
    </footer>
  </div>
  
</template>

<script>
import inputTexto from "./components/inputText.vue";
import selectCicom from "./components/selectCicom.vue";
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap";

export default {
  
  name: "App",
  metaInfo: {
      title: 'Incidentes CICOMs',
  },
  created(){
    // muda o titulo da aba do navegador
    document.title = "Incidentes CICOMs"
    },
  data() {
    return {
      dataIncidente: "",

      incidente: "incidente",
      whatsapp: "whatsapp",

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
    geraHora() {
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

    preencherCampos() {
      this.geraHora();
      const indiceCicom =
        document.getElementById("lista-cicoms").selectedIndex - 1;

      this.textoWhatsapp = `Foi aberto um Incidente junto à PRODEB referente à queda do link de DADOS da CICOM ${this.cicoms[
        indiceCicom
      ].cicom.toUpperCase()}.\nIncidente Nº: `;

      this.textoInciente = `CICOM ${this.cicoms[
        indiceCicom
      ].cicom.toUpperCase()}.\nInformamos que às ${
        this.dataIncidente
      } foi constatado que o link de DADOS da CICOM da cidade de ${this.cicoms[
        indiceCicom
      ].cicom.toUpperCase()}, de circuito ${this.cicoms[
        indiceCicom
      ].circuito.toUpperCase()}, encontra-se inoperante. \nInformamos ainda que o atendimento é de emergência, operando 24h e não pode parar.\nTelefone / Contato: ${
        this.cicoms[indiceCicom].Tel
      } / Coordenador ou Adjunto da CICOM.\nChamado aberto por `;
    },
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
</style>

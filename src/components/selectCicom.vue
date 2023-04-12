<template>
  <div>
    <select class="lista-cicoms">
        <option>Selecione uma Cicom</option>
        <option v-for="cicom in cicoms" :key = 'cicom.circuito' :value = 'cicom.cicom'>
            {{ cicom.cicom }} - {{ cicom.circuito }}
        </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "selectCicom",
  data() {
    return {
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
  methods: {
    preencheCampos: ()=>{
        console.log(this.cicoms.cicom);
    }
  }
};
</script>

<style>
.lista-cicoms{
    width: 1046px;
    height: 35px;
    margin-bottom: 10px;
}
</style>

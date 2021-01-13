<template>
    <h2>Tipo de cuenta: {{cuenta}}</h2>
    <h2>Saldo: {{saldo}}</h2>
    <h2>Cuenta: {{ estado ? "Activa" : "Descativada"  }}</h2>
    <div v-for="(servicio, index) in servicios" :key="index">
      {{index}} -- {{ servicio }}
    </div>

    <AccionSaldo 
        texto="Aumentar Saldo"
        @accion="aumentar"
        
    />
    <AccionSaldo 
        texto="Disminuir Saldo"
        @accion="diminuir"
        :disabled="disabled"
    />
</template>

<script>
import AccionSaldo from './AccionSaldo.vue'
export default {
    components:{
        AccionSaldo,
    },
    data() {
        return {
            saldo: 1000,
            cuenta: "visa",
            estado:true,
            servicios: ["giro","abono","trasferencia"],
            disabled:false,

        }
    },
    methods:{
        aumentar(){
            this.saldo= this.saldo+100;
            this.disabled=false;
        },
        diminuir(){
            if(this.saldo===0){
                this.disabled=true;
                alert("Saldo agotado")
            }
            else{
                 
                this.saldo= this.saldo-100;
            }
        }
    }

}
</script>

<style>

</style>
<template>
    <h2>Tipo de cuenta: {{cuenta}}</h2>
    <h2>Saldo: {{saldo}}</h2>
    <h2>Cuenta: {{ estado ? "Activa" : "Descativada"  }}</h2>
    <div v-for="(servicio, index) in servicios" :key="index">
      {{index}} -- {{ servicio }}
    </div>
</template>

<script>
export default {
    data() {
        return {
            saldo: 1000,
            cuenta: "visa",
            estado:true,
            servicios: ["giro","abono","trasferencia"],

        }
    },
}
</script>

<style>

</style>
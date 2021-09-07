<template>
<div>
  <h2>Tipo de cuenta: {{cuenta}}</h2>
  <h1>Saldo: {{saldo}}</h1>
  <h2>Cuenta {{estado ? 'Activa': 'Desactivada'}}</h2>
  <!-- Cada uno de los servicios se va a comportar como un service(item) y apuntara -->
  <!--El index es como el numero de servicio empieza de 0-->
  <!--v-for es como recursión-->
  <div v-for="(service,index) in servicios" :key="index">
    {{index+1}} - {{ service }}
  </div>
  <!--Mandamos props al hijo Acción Saldo -->
  <!-- UTILIZANDO CUSTOM EVENT SON LOS @ se cream cpm cualquier nombre, EL @ HACE REFERENCIA A UN MÉTODO
  Y LO QUE DENTRO DE LAS COMILLAS EL EL MÉTODO DECLARADO AQUI methods:-->
  <!--Pasamos props otra vez del botón desactivarpaso-->
  <AccionSaldo texto="Aumentar Saldo" @accionaum="aumentar" :botondesactivarpaso='botondesactivar'/>
  <!--Reutilizamos-->
  <AccionSaldo texto="Disminuir Saldo" @accionaum="disminuir" :botondesactivarpaso='botondesactivar'/>
</div>
</template>

<script>
//Aquí llamamos al otro componente hijo AccionSaldo.vue (otro componente)
import AccionSaldo from './AccionSaldo.vue'
export default {
  //llamamos a component que jalamos el AccionSaldo
  components: {
    AccionSaldo
  },
  data() {
    return {
      saldo: 1000,
      cuenta: 'Visa',
      estado: true,
      servicios: ['giro','abono','transferencia'],
      botondesactivar: false
    }
  },
  methods: {
    aumentar() {
      this.botondesactivar = false
      this.saldo = this.saldo + 100
    },
    disminuir() {
      if(this.saldo === 0){
        //this.botondesactivar = true ARREGLEMOS ESTO
        alert('Saldo Agotado')
      }else{
      this.saldo = this.saldo - 100
      }
    }
  }
}
</script>

<style>

</style>
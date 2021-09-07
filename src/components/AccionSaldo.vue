<template>
<div>
<!--Utilizamos @click este identifica una acción en este caso el button-->
    <!--<button @click="this.$emit('accionaum')">{{texto}}</button>-->
    <!--Si no funciona el de arriba esta este-->
   <!-- <button v-on:click="$emit('accionaum')">{{ texto }}</button>-->
   <!--<button @click="accionaum">{{ texto }}</button>-->
   <button @click="accionaum" :disabled="botondesactivarpaso">{{ texto }}</button>
</div>
</template>

<script>
export default {
    props: {
        texto: String,
        //Detallando
        botondesactivarpaso: {
            type: Boolean,
            default: false 
        }
    },
    methods: {
        accionaum(){
            this.$emit('accionaum')
        }
    }
}
</script>

<style>

</style>
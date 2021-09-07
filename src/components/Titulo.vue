<template>
<!--pasamos el props text desde aqui en vez de texto normal-->
  <h1>{{ texto }}</h1>
</template>

<script>

export default {
    //props: ['texto']
    props: {
        //agarramos el texto mandado por props de App.vue
        texto: String
    }
    
}
</script>

<style scoped>
/* scoped es solo para que los estilos solo afecte a este componente */
h1 {
  color: peru;
}

</style>
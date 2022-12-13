<template >

  <section class="src-componentes-conversor">
    <h1>Conversor a dólares</h1>

    <span>Ingrese monto $</span>  <input type="text" v-model="pesos"> <br>
    <br>
    <span>Valor del dolar en $</span>  <input type="text" v-model="valorDolar"> <br><br>
    <span>Valor convertido USD </span> {{pesos/valorDolar}} <br> <br>

         <br>
      <h4> Respuestas a las preguntas </h4>

      <p> respuestas : 1  , 2 ,3 ,4 ,5 

  </section>

</template>

<script>

  export default  {
    name: 'src-componentes-conversor',
    props: [],
    mounted () {

    },
    data () {
      return {
        pesos:0,
        valorDolar:300

      }
    },
    methods: {

    },
    computed: {

    }
}


</script>

<style scoped lang="css">
  .src-componentes-conversor {

  }
</style>

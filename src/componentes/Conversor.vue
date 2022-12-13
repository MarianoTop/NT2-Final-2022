<template >

  <section class="src-componentes-conversor">
    <h1>Conversor a dólares</h1>

    <span>Ingrese monto $</span>  <input type="text" v-model="pesos"> <br>
    <br>
    <span>Valor del dolar en $</span>  <input type="text" v-model="valorDolar">  
    <span> Actualizacion </span> <input type="checkbox" v-model="actualizacionAutomatica">
    
    <br><br>
    
    <span>Valor convertido USD </span> {{pesos/valorDolar}} <br> <br>

         <br>
      <h4> Respuestas a las preguntas </h4>

      <p> Respuestas;  1:c  , 2:b ,3:c ,4:a ,5:c  </p>

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
        valorDolar:300,
        urlDolarPrecio: 'https://www.dolarsi.com/api/api.php?type=valoresprincipales',
        actualizacionAutomatica:false

      }
    },
    methods: {

      async getCotizacion() {
        try {
          let response = await this.axios(this.urlDolarPrecio)
          let respuesta = response.data

         

          let cotizacionBlue=respuesta.find( function(x){
            
            return x.casa.nombre=='Dolar Blue'
          })

          let valorBlueApi= cotizacionBlue.casa.compra
          
          return valorBlueApi
         

        }
        catch(error) {
           console.error('Se produjo un error al obtener la cotizacion', error)
        }
      },
       
    },
    computed: {

      

    }
}


</script>

<style scoped lang="css">
  .src-componentes-conversor {

  }
</style>

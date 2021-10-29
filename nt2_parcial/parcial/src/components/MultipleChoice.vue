<template lang>

  <section class="src-components-multiple-choice">
    <div class="jumbotron" mt-3>
    <table class="table">
      <tr>
        <th>Número de pregunta</th>
        <th>Respuesta</th>
      </tr>
      <tr v-for="(respuesta,index) in preguntas" :key="index">
        <td>{{respuesta.numero}}</td>
        <td>{{respuesta.respuestas}}</td>
      </tr>
      <!--<tr>
        <td></td>
        <td></td>
      </tr>
      <tr>
        <td></td>
        <td></td>
      </tr>-->
    </table>
    </div>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-multiple-choice',
    props: [],
    mounted () {

    },
    data () {
      return {
        preguntas: [
          { numero: 1, respuestas: ['b','d'] },
          { numero: 2, respuestas: ['c'] },
          { numero: 3, respuestas: ['b','e'] },
        ]

      }
    },
    methods: {

    },
    computed: {

    }
}


</script>

<style scoped lang="css">
  .src-components-multiple-choice {
    color: black
  }
  .table{
    align-content: center;
  }
</style>

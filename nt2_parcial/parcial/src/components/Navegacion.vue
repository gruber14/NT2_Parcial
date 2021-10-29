<template lang>

  <section class="src-components-navegacion">
    <nav class="navbar navbar-expand-md navbar-dark bg-dark">
      <router-link to="/">
        <a class="navbar-brand" href="#">Inicio</a>
        </router-link>
      <ul class="navbar-nav">
        
        <li class="nav-item">
          <router-link to="/Formulario">
          <a class="nav-link" href="#">Formulario</a>
          </router-link>
        </li>
        <li class="nav-item">
          <router-link to="/MultipleChoice">
          <a class="nav-link" href="#">Multiple choice</a>
          </router-link>
        </li>
      </ul>
    </nav>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-navegacion',
    props: [],
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {

    },
    computed: {

    }
}


</script>

<style scoped lang="css">
  .src-components-navegacion {
    color: black;

  }
</style>

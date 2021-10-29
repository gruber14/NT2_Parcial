<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">-->
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Navegacion></Navegacion>
<router-view> </router-view>


  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import Formulario from './components/Formulario.vue'
//import MultipleChoice from './components/MultipleChoice.vue'
import Navegacion from './components/Navegacion.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld
    //Formulario,
    //MultipleChoice,
    Navegacion,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

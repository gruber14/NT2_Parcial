<template lang>

  <section class="src-components-formulario">
    <vue-form :state="formstate" @submit.prevent="enviar()">

        <validate tag="div">
        <label for="nombre">Nombre</label>
     <input type="text" 
     id="nombre" 
     v-model="formData.nombre" 
     required name="nombre" 
     autocomplete="off" 
     class="form-control"
     v-model.trim="formData.nombre" />
     <field-messages name="nombre" show="$dirty">
            <div slot="required" class="alert alert-danger mt-1">Por favor complete este campo.</div>
          </field-messages>
        </validate>

       <validate tag="div">
        <label for="descripcion">Descripción</label>
     <input type="text" 
     id="descripcion" 
     v-model="formData.descripcion" 
     required name="descripcion" 
     autocomplete="off" 
     class="form-control"
     v-model.trim="formData.descripcion" />
     <field-messages name="descripcion" show="$dirty">
            <div slot="required" class="alert alert-danger mt-1">Por favor complete este campo.</div>
          </field-messages>
        </validate>

       <validate tag="div">
        <label for="importe">Importe</label>
     <input type="number" 
     id="importe" 
     v-model="formData.importe" 
     required name="importe" 
     autocomplete="off" 
     class="form-control"
      />
     <field-messages name="importe" show="$dirty">
            <div slot="required" class="alert alert-danger mt-1">Por favor complete este campo.</div>
          </field-messages>
        </validate>

        <button class="btn btn-primary my-3" :disabled="formstate.$invalid" type="submit">Enviar</button>
    </vue-form>

   <div class="form-group">
        <label for="presupuesto">Presupuesto</label>
        <input type="text"
        id='presupuesto'
        class='form-control'
        v-model.number="presupuesto"    
        >
   </div>

    <table class="table">
      <tr>
        <th>Nombre</th>
        <th>Descripción</th>
        <th>Importe</th>
        <th>Fecha</th>
      </tr>
      <tr v-for="(imp,index) in importes" :key="index">
        <td>{{imp.nombre}}</td>
        <td>{{imp.descripcion}}</td>
        <td>{{imp.importe}}</td>
        <td>{{imp.fecha}}</td>
      </tr>
      <br>
      <tr :style="{color: colorearImporteTotal(sumarImportes())}">Importes totales: {{sumarImportes()}}</tr>
    </table>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-formulario',
    props: [],
    mounted () {

    },
    data () {
      return {
                formstate : {},

        importes: [],
        formData : this.inicializarImportes(),
        presupuesto: null
      }
    },
    methods: {
      enviar(){
        let importe = {...this.formData}
        importe.fecha = new Date().toLocaleString()
        this.formData = this.inicializarImportes()
        this.importes.push(importe)
        this.formstate._reset()

      },
      inicializarImportes(){
        return {
          nombre: null,
          descripcion: null,
          importe: null,
        }
      },
      sumarImportes(){
        let suma=parseInt(0);
        for (let i=0; i<this.importes.length;i++){
          suma= parseInt(suma) + parseInt(this.importes[i].importe);
        }
        return suma;
      },
      colorearImporteTotal(total){
        let color= '#cf3476';
        if (total<1000){
          color='#00FF00'
        }
        if (total>5000){
          color='#ffa500';
        }
        if (total>this.presupuesto && this.presupuesto!=null){
          color='#ff004f';

        }
        return color;

      },

    },
    computed: {

    }
}


</script>

<style scoped lang="css">
  .src-components-formulario {
  color:black
 
  }
</style>

<template>
  <div id="app">
    <Tareas @enviandoTarea='procesarTarea'/>
    <Lista :datosTareas='nuevasTareas' @eliminarTarea='quitarTarea'/>
  </div>
</template>

<script>
import Tareas from './components/Tareas.vue';
import Lista from './components/Lista.vue';


export default {
  name: 'App',
  data() {
    return {
      nuevasTareas: []
    }
  },
  components: {
    Tareas,
    Lista
  },
  methods: {
    procesarTarea(datos){
      console.log(datos);
      this.nuevasTareas.push(datos);
    },
    quitarTarea(index){
      this.nuevasTareas.splice(index,1);
      this.$swal('¡Tarea Eliminada!');
    }
  },
}
</script>

<style>

</style>

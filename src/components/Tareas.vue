<template>
  <div>
    <nav class="navbar justify-content-center navbar-dark bg-dark
    ">
      <span class="navbar-brand mb-0 h1 text-uppercase">Lista de Tareas</span>
    </nav>
    <form class="form-inline justify-content-center" @submit.prevent="agregarTarea">
      <div class="form-group mb-2">
        <h2 for="tarea">Tarea</h2>
      </div>
      <div class="form-group mx-sm-3 mb-2">
        <input type="text" v-model="tarea" class="form-control" placeholder="ingrese nueva tarea">
      </div>
      <button type="submit" class="btn btn-primary mb-2">Añadir</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Tareas',
  data() {
    return {
      tarea: ''
    }
  },
  methods: {
    agregarTarea() {
      if(this.tarea) {
        let datosTareas = this.tarea;
        this.$emit('enviandoTarea', datosTareas);
        this.tarea = '';
      } else {
        console.log('no hay tareas');
      }
    }
  },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

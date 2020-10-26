<template>
    <div>
        <div class="container">
            <ul class="list-group text-center" >
                <li class="list-group-item" v-for="(hacer, index) in datosTareas" :key="index">{{hacer}} <button type="submit" class="btn btn-danger mb-2" @click.prevent="eliminarTarea(index)">Eliminar</button></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Lista',
    props: {
        datosTareas: {
            type: Array,
            required: true
        }
    },
    methods: {
        eliminarTarea(index){
            let confirmar = confirm('¿Terminaste esta tarea?')
            if(confirmar){
                this.$emit('eliminarTarea', index);
            }
        }
    },
}
</script>

<style>

</style>
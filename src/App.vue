<template>
  <div id="app">
    <div>
      <h1>Agrega una tarea a tu lista</h1>
    <input type="text" v-model="tarea" @keyup.enter="add">
    <button @click="add">Agregar tarea</button>
    </div>
    <hijo :lista_tareas="lista_tareas" @descartar="descartar"></hijo>
  </div>
</template>

<script>
import Hijo from './components/Hijo.vue'

export default {
  name: 'App',
  components: {
    Hijo
  },
  data() {
    return {
       tarea: " ",
      lista_tareas: []
    }
  },
  methods: {
    add(){
      this.lista_tareas.push(this.tarea),
      this.tarea = ''
    },
    descartar(index){
      this.lista_tareas.splice(index, 1)
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: black;
}
</style>

<template>
  <div>
    <ul>
      <li v-for="tarea in lista_tareas" :key="tarea">{{tarea}} <button @click="descartar(tarea)">Eliminar tarea</button> </li>
    </ul>   
  </div>
</template>

<script>
export default {
  name: 'hijo',
  props: {
    lista_tareas: Array,
    tarea: String,
  },
  
  methods:{
     descartar(tarea){
      this.$emit("descartar", tarea)
    }
  }
  
}
</script>


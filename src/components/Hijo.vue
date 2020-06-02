<template>
  <div>
    <ul>
      <li v-for="(tarea, index) in lista_tareas" :key="index">{{tarea}} <button @click="descartar(index)">Eliminar tarea</button> </li>
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
     descartar(index){
      this.$emit("descartar", index)
    }
  }
  
}
</script>


<template>
  <div>
    <h1>{{ nombreLista }}</h1>
    <H3>Reenombrar</H3>
    <input v-model="nombreLista" placeholder="Nombre de la lista" />
    
    <div>   
      <H3>Agregar Tarea</H3>
       <input v-model="nuevaTarea" placeholder="Nueva Tarea" />
    <button @click="agregar">Agregar Tarea</button>
</div>

    <ul>
      <li v-for="(tarea, index) in tareas" :key="index">
        <input v-model="tarea.nombre" />
        <button @click="eliminar(index)">Eliminar</button>
      
      </li>
    </ul>
  </div>
</template> 

<script>
export default {
  data() {
    return {
      nombreLista: "Lista de quehaceres",
      tareas: [
       
      ],
      nuevaTarea: "",
    };
  },
  methods: {
    renombrar(){

    },
    agregar() {
      this.tareas.push({ nombre: this.nuevaTarea });
      this.nuevaTarea = "";
    },
    eliminar(index) {
      this.tareas.splice(index, 1);
    }
  },
};
</script>


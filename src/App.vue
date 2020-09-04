<template>
	<div>
    <h3>Lista de Tareas de Agus</h3>
		<input v-model="tarea" type="text" placeholder="Apunta tu Tarea"/>
		<button @click="add">Añadir Tarea</button>
		<Tarea v-for="(tarea, i) in tareas" :key="i" :tarea="tarea" :indice="i" @eliminar="eliminarTarea"></Tarea>
	</div>
</template>

<script>
import Tarea from './components/Tarea';

export default {
	name: 'Tareas',
	components: {
		Tarea,
	},
	data() {
		return {
			tarea: '',
			tareas: [],
		};
	},
	methods: {
		add() {
			this.tareas.push(this.tarea);
			this.tarea = ' ';
		},
		eliminarTarea(indice) {
			this.tareas.splice(indice, 1);
		},
	},
};
</script>

<style>
body{
  font-family: 'Lucida Sans';
  font-size: 20px;
  
}
 button{
   background-color: coral;
   color: white;
   padding: 15px;
   border-radius: 5px;
 }
 input{
   padding: 15px;
 }
</style>

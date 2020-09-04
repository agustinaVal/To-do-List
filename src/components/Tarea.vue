<template>
	<div>
		<ul>
            <li>{{ tarea }}</li>
        </ul>
		<button @click="vaciar">Eliminar</button>
	</div>
</template>

<script>
export default {
	name: 'Tarea',
	props: {
		tarea: String,
		indice: Number,
	},
	methods: {
		vaciar() {
			this.$emit('eliminar', this.indice);
		},
	},
};
</script>

<style></style>

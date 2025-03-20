<script setup>
	import { ref } from 'vue'
	import FlipCard from './FlipCard.vue';
	const rows = 2;
	const array = ref([
		1, 4, 3, 4,
		2, 3, 1, 2
	])
</script>

<template>
	<table>
		<tr v-for="n in rows">
			<th v-for="m in array.length/2"><FlipCard :cardContent="array[m-1 + (n-1)*4]"/></th>
		</tr>
	</table>
</template>
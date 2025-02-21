<script setup>
	import { ref } from 'vue'

	defineProps({
		item: String,
	})
	const count = ref(0);
</script>

<template>
	<p>
		{{ item }}: {{ count }}
		<button @click="count++">+</button> 
		<button @click="count--">-</button> 
	</p>
</template>
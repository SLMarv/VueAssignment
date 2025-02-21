<script setup>
	import { ref } from 'vue'
	import Image from 'primevue/image';
	import Panel from 'primevue/panel';

	const numberOfFiles = 5;
	var images = new Array(numberOfFiles);
	for (let index = 0; index < numberOfFiles; index++) {
		images[index] = "Gallery/" + index + ".jpg"		
	}
	const rows = ref(Math.ceil(numberOfFiles/3.0));
</script>

<template>
	<table>
		<tr v-for="n in rows">
			<th><Image :src="images[(n-1)*3]" alt="Image" width="250" height="250" preview/></th>
			<th v-if="images.length >(n-1)*3+1"><Image :src="images[(n-1)*3+1]" alt="Image" width="250" height="250" preview/></th>
			<th v-if="images.length >(n-1)*3+2"><Image :src="images[(n-1)*3+2]" alt="Image" width="250" height="250" preview/></th>
		</tr>
	</table>
</template>
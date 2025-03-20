<script setup>
	import { ref } from 'vue'
	import Card from 'primevue/card';
	var isActive = ref(true);
	var show = ref(true);
	defineProps({
		cardContent: Number,
	})
</script>

<template class="flip-box">
	<Transition>
		<Card @click="isActive = !isActive" :class="{ 'flip-box-front': !isActive, 'flip-box-back': isActive }">
			<template  #content>
				<p :class="{'hidden flip-box-back': isActive, 'flip-box-front': !isActive }">{{cardContent}}</p>
			</template>
		</Card>
	</Transition>
</template>

<style scoped>
/* The flip box container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-box {
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
}

/* This container is needed to position the front and back side */
.flip-box-front, .flip-box-back, .hidden {
	transition: all 0.8s;
	transform-style: preserve-3d;
}

.hidden{
	opacity: 0;
	-webkit-backface-visibility: hidden; /* Safari */
	backface-visibility: hidden;
}

/* Style the front side */
.flip-box-front {
  background-color: #bbb;
  color: black;
}

/* Style the back side */
.flip-box-back {
  background-color: dodgerblue;
  color: white;
  transform: rotateY(180deg);
}



</style>
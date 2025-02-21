<script setup>
import Counter from './components/Basic-website/Counter.vue';
import Gallery from './components/Gallery/Gallery.vue';
</script>

<template>
  <Gallery style="width: 50%; margin: 0 auto;"/>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>

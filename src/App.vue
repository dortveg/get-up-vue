<template>
  <Counter />
  <Generator />
  <Footer />
</template>

<script>
import Counter from './components/Counter.vue';
import Generator from './components/Generator.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: { Counter, Generator, Footer }
}
</script>

<style>
@font-face {
  font-family: 'Syne';
  src: url(./assets/SyneMono-Regular.ttf);
}
@font-face {
  font-family: 'Julius';
  src: url(./assets/JuliusSansOne-Regular.ttf);
}
@font-face {
  font-family: 'Bungee';
  src: url(./assets/Bungee-Regular.ttf);
}

html {
  height: 100%;
  background-color: #141313;
}
</style>

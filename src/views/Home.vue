<template>
  <div class = "home">
    <Menu />
    <Important />
    <Gallery />
  </div>
</template>

<script>
import Gallery from '@/components/Gallery.vue';
import Important from '@/components/Important.vue';
import Menu from '@/components/Menu.vue';

export default {
  title: 'Regina Grozdova portfolio',
  name: 'home',
  components: {
    Important,
    Gallery,
    Menu,
  },
};
</script>

<style>
  body {
    background-color: #FFDB88;
    margin: 0 0 0 0;
  }
</style>

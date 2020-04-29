<template>
  <div class = "home">
    <Menu />
    <Important />
    <Gallery />
    <p class = "bottom">Copyright Regina Grozdova</p>
  </div>
</template>

<script>
import Gallery from '@/components/Gallery.vue';
import Important from '@/components/Important.vue';
import Menu from '@/components/Menu.vue';

export default {
  title: 'Regina Grozdova portfoolio',
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
    background-color: #EA80FF;
    margin: 0 0 0 0;
  }
  .bottom {
    font-size: 10px;
    bottom: 2px;
    text-align: center;
  }
</style>

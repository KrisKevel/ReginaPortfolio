<template>
  <div class = "gallery-all">
    <div class = "gallery-text">
      <span> Teised tööd </span>
    </div>
    <div class="gallery">
      <div class="gallery-panel"
          v-for="photo in photos"
          :key="photo.id">
        <router-link :to="`/photo/${photo.id}`">
          <img :src="thumbUrl(photo.filename)">
        </router-link>
        <p class = "outer" v-if="photo.outside">{{ photo.outside }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import photos from '@/photos.json';

export default {
  name: 'Gallery',
  data() {
    return {
      photos,
    };
  },
  methods: {
    thumbUrl(filename) {
      return require(`../assets/images/thumbnails/${filename}`);
    },
  },
};
</script>

<style>
  .outer {
    margin-top: 0;
    font-size: 15px;
  }

  .gallery-text{
    margin: 0 0 0 5rem;
    text-shadow: 1px 1px 1px rgb(0, 0, 0, 0.4);
  }

  .gallery-all {
    margin: 5rem auto;
  }

  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(10rem, 1fr));
    grid-gap: 5px;
    max-width: 50rem;
    margin: 1rem auto;
    padding: 0 5rem;
  }

  .gallery-panel img {
    width: 100%;
    height: 22vw;
    object-fit: cover;
  }
</style>

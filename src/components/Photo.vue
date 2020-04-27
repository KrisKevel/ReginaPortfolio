<template>
  <div class="lightbox" @click.self="closeLightbox">
    <img :src="photoUrl(photo.filename)">
    <div class="lightbox-info">
      <div class="lightbox-info-inner">
        <p v-if="photo.inside">{{ photo.inside }}</p>
        <p v-if="photo.autor.name">{{ photo.autor.name }}</p>
        <p v-if="photo.photographer">
          <a rel="nofollow" :href="photo.photographer.url">{{ photo.photographer.name }}</a>
        </p>
        <p v-if="photo.source">
          via <a rel="nofollow" :href="photo.source.url">{{ photo.source.name }}</a>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import photos from '@/photos.json';

export default {
  name: 'Photo',
  data() {
    return {
      photos,
    };
  },
  computed: {
    photo() {
      return this.photos.find((photo) => {
        return photo.id === Number(this.$route.params.id);
      });
    },
  },
  methods: {
    photoUrl(filename) {
      return require(`../assets/images/${filename}`);
    },
    closeLightbox() {
      this.$router.push('/');
    },
  },
};
</script>

<style>

  .lightbox {
    position: fixed;
    top: 0;
    left: 0px;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.8);
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 200px;
  }

  .lightbox img {
    margin: auto 0 auto 5rem;
    max-height: 100%;
    width: 220%;
    grid-column-start: 1;
  }

  .lightbox-info {
    margin: auto 5rem auto 0rem;
    grid-column-start: 3;
  }

  .lightbox-info-inner {
    background-color: #FFFFFF;
    display: inline-block;
    padding: 2rem;
  }
</style>

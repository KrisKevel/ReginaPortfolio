<template>
    <div class = "important-all">
        <div class = "important-text">
        <span> Tähtsad tööd </span>
        </div>
        <div class="important">
            <div class="important-panel"
                v-for="photo in important"
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
import important from '@/important.json';

export default {
  name: 'Important',
  data() {
    return {
      important,
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
    .important-text{
        margin: 0 0 0 5rem;
    }

    .important-all {
        margin: 5rem auto;
    }

  .important {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(20rem, 1fr));
    grid-gap: 20px;
    max-width: 75rem;
    margin: 1rem auto;
    padding: 0 5rem;
  }

  .important-panel img {
    width: 100%;
    height: 25vw;
    object-fit: cover;
  }
</style>
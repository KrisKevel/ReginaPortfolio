<template>
    <div class = "important-all">
        <div class = "important-text">
            <span> Kohustuslikud tööd </span>
        </div>
        <div class="important">
            <div class="important-panel" v-for="photo in important":key="photo.id">
                <router-link :to="`/photo/${photo.id}`">
                    <img :src="thumbUrl(photo.filename)">
                </router-link>
                <p class = "outer" v-if="photo.outside">{{ photo.outside }}</p>
            </div>
            
            <div class = "centered">
                <router-link :to="`/photo/4`">
                    <img :src="thumbUrl('plants.jpg')">
                </router-link>
                <p class = "outer">Mänguruum tegelaskujudega "5pm"</p>
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
    .centered{
      margin: 0 0 0 9rem;
      width: 50%;
      padding: 10px;
      height: 30vw;
    }

    .centered img{
      height: 30vw;
    }
    
    .important-text{
        margin: 0 0 0 5rem;
    }

    .important-all {
        margin: 5rem auto;
    }

    .important {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(10rem, 1fr));
      grid-gap: 5px;
      max-width: 50rem;
      margin: 1rem auto;
      padding: 0 5rem;
      position: relative;
    }

    .important-panel img {
      width: 100%;
      height: 30vw;
      object-fit: cover;
    }

    .important-panel{
      transform: translate(0%, 0%);
    }
</style>
<script setup>
import { ref } from 'vue';
import UploadImage from './components/UploadImage.vue';

const image = ref('')

function getImage(file) {
  const url = URL.createObjectURL(file)
  image.value = url
}
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <UploadImage @pass-image="getImage" />
  <img
    v-if="image.length"
    :src="image"
    class="image"
    alt="example">
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
.image {
  margin-top: 24px;
  width: 300px;
  height: 240px;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>

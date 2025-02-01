<script setup lang="ts">
import { ref } from "vue";

const pages = ref([
  {
    name: "Home",
    id: 0,
    status: true,
  },
]);

const togglePage = (id: number) => {
  pages.value.forEach((page) => {
    if (page.id === id) {
      page.status = true;
    } else {
      page.status = false;
    }
  });
};
</script>

<template>
  <header>
    <h1>NeoTeak</h1>
    <button v-for="page in pages" :key="page.id" :class="page.status ? 'now' : ''" @click="togglePage(page.id)">
      {{ page.name }}
    </button>
  </header>

  <div id="Home" v-if="pages[0].status">
    <div class="article">
      <h1>NeoTeak</h1>
      <article>Welcome! This is my website!</article>
    </div>
  </div>
</template>

<style scoped></style>

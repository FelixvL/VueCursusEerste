<script setup>
import { items } from "./movies.json";
import MovieOnderdeel from './components/MovieOnderdeel.vue'
import { reactive } from 'vue'
/*
 This is an Icon that you can use to represent the stars if you like
 otherwise you could just use a simple ⭐️ emoji, or * character.
*/
// import { StarIcon } from "@heroicons/vue/24/solid";
const films = reactive(items);
</script>
<style scoped>
.flex-container {
  display: flex;
  flex-wrap: nowrap; /* Prevents wrapping to the next line */
  align-items: stretch;
  justify-content: center; /* Centers items horizontally if they don't fill the entire width */
}
</style>
<template>
  <!-- This is where your template goes	-->
  <div class="flex-container">
      <MovieOnderdeel v-for="(item, index) in films" :key="item.id" :defilm="item" :index="index"/>
  </div>
</template>

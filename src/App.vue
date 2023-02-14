<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div class="container mx-auto">
    <RouterLink to="/">
      <button class="m-1 bg-black text-white px-5 py-3 rounded-md">HOME</button>
    </RouterLink>

    <RouterLink to="/todo">
      <button class="m-1 bg-black text-white px-5 py-3 rounded-md">TODO</button>
    </RouterLink>

    <RouterView />
  </div>
</template>

<style scoped></style>

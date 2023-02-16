<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div class="container mx-auto">
    <RouterLink to="/">
      <button class="m-1">HOME</button>
    </RouterLink>

    <RouterLink to="/todo">
      <button class="m-1">TODO</button>
    </RouterLink>

    <RouterView />
  </div>
</template>

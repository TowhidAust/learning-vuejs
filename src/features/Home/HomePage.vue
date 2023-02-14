<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <section class="flex items-center justify-center mt-5">
    <div class="max-w-sm mx-auto p-8 bg-stone-300 rounded-xl shadow-md">
      <div
        class="bg-black rounded-full flex items-center justify-center container mx-auto mb-5 h-24 w-24"
      >
        <img class="ring-green-400 w-12" src="@/assets/logo.svg" alt="logo" />
      </div>
      <div class="text-lg text-center">
        <div>
          <p class="text-center">TODO APP</p>
          <p class="text-justify">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora,
            hic repellat voluptatibus ab iure, expedita numquam aut sequi iusto
            ea officiis nostrum dolores eum, ex sapiente est id deleniti
            assumenda?
          </p>
        </div>
        <RouterLink to="/todo">
          <button
            class="text-center px-4 py-2 border border-red-600 rounded-full text-sm w-full mt-5 bg-black text-white"
          >
            Visit now
          </button>
        </RouterLink>
      </div>
    </div>
  </section>
</template>

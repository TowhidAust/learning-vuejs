<template>
  <div>
    <TodoList />
  </div>
  <router-view></router-view>
</template>

<script>
import TodoList from "./features/TodoList.vue";
export default {
  name: "App",
  components: {
    TodoList,
  },
};
</script>

<style></style>

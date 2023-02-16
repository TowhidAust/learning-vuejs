<template>
  <section
    :class="[
      task.reminder ? 'reminder' : '',
      'task shadow-md mt-2 bg-black text-white rounded-sm p-3',
    ]"
    :key="task.id"
    v-for="task in tasks"
  >
    <font-awesome-icon
      class="absolute right-0 top-0 cursor-pointer m-2 z-10"
      :icon="['fas', 'user-secret']"
      size="md"
      color="red"
    />
    <div>
      {{ task.text }}
    </div>
    <div>
      <small>{{ task?.day }}</small>
    </div>
  </section>
</template>

<script>
export default {
  name: "TaskList",
  props: {
    tasks: Array,
  },
  created() {
    console.log(this.tasks);
  },
};
</script>

<style scoped>
.task.reminder {
  border-left: 5px solid green;
}
</style>

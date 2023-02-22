<template>
  <section
    :class="[
      task.reminder ? 'reminder' : '',
      'task bg-slate-200 shadow  mt-2  rounded-sm p-3',
    ]"
    :key="task.id"
    v-for="task in tasks"
    @dblclick="$emit('toggle-reminder', task.id)"
  >
    <font-awesome-icon
      @click="$emit('delete-task', task.id)"
      class="absolute right-0 top-0 cursor-pointer m-3 z-10"
      icon="fa-solid fa-trash"
    />
    <div class="pr-6">
      <div>
        <small>{{ task?.day }}</small>
      </div>
      <div class="text-justify">
        {{ task.text }}
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "TaskList",
  props: {
    tasks: Array,
  },
  methods: {
    // onDelete(id) {
    //   this.$emit("delete-task", id);
    // },
  },

  emits: ["delete-task", "toggle-reminder"],
};
</script>

<style scoped>
.task.reminder {
  border-left: 5px solid rebeccapurple;
}
</style>

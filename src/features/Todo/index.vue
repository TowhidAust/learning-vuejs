<template>
  <div class="todo-container p-5">
    <div class="">
      <CustomButton text="ADD TODO" color="red" type="primary" />
    </div>
    <div>
      <TaskList :tasks="tasks" />
    </div>
  </div>
</template>

<script>
import CustomButton from "../../components/CustomButton.vue";
import TaskList from "./TaskList.vue";
export default {
  name: "TodoButton",
  components: {
    CustomButton,
    TaskList,
  },

  data() {
    return {
      tasks: [],
    };
  },

  created() {
    this.tasks = [
      {
        id: 1,
        text: "This is a task 1",
        day: "Jan 1st at 2.30pm",
        reminder: true,
      },
      {
        id: 2,
        text: "This is a task 12",
        day: "Feb 2st at 3.30pm",
        reminder: false,
      },
    ];
  },
};
</script>

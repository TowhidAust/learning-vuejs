<template>
  <div class="todo-container p-5">
    <div class="">
      <CustomButton text="ADD TODO" color="red" type="primary" />
    </div>
    <div>
      <!-- Here v-bind will take the variable instead of string from data -->
      <TaskList
        @delete-task="deleteTask"
        @toggle-reminder="toggleReminder"
        :tasks="tasks"
      />
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

  methods: {
    deleteTask(id) {
      if (confirm("Are you sure?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
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
        text: "Nostrud exercitation mollit excepteur incididunt.",
        day: "Jan 1st at 2.30pm",
        reminder: true,
      },
      {
        id: 2,
        text: "Cillum nisi exercitation ad proident.",
        day: "Jan 1st at 2.30pm",

        reminder: false,
      },
      {
        id: 3,
        text: "Lorem voluptate nulla ullamco deserunt dolore duis quis culpa sunt tempor sunt.",
        day: "Jan 1st at 2.30pm",
        reminder: true,
      },
      {
        id: 4,
        text: "Amet est mollit excepteur esse tempor nulla.",
        day: "Jan 1st at 2.30pm",
        reminder: false,
      },
    ];
  },
};
</script>

<template>
  <div class="todo-container p-5">
    <AddTask @add-task="addTask" />
    <div>
      <!-- Here :task will take the variable instead of string from data -->
      <TaskList
        @delete-task="deleteTask"
        @toggle-reminder="toggleReminder"
        :tasks="tasks"
      />
    </div>
  </div>
</template>

<script>
import TaskList from "./TaskList.vue";
import AddTask from "./AddTask.vue";
export default {
  name: "TodoButton",
  components: {
    TaskList,
    AddTask,
  },

  methods: {
    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
    addTask(task) {
      this.tasks = [...this.tasks, task];
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

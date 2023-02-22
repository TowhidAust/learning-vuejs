<template>
  <form action="#" @submit="onSubmitForm">
    <div class="mt-2">
      <input
        v-model="text"
        class="border border-black rounded-sm px-3 py-1.5 outline-none"
        placeholder="Add Task"
        type="text"
        name="text"
      />
    </div>

    <div class="mt-2">
      <input
        v-model="day"
        class="border border-black rounded-sm px-3 py-1.5 outline-none"
        placeholder="Set Date & Time"
        type="text"
        name="day"
      />
    </div>

    <div class="mt-2">
      <label for="">Set Reminder</label>
      <input
        v-model="reminder"
        class="border border-black rounded-sm px-3 py-1 ml-2 outline-none"
        type="checkbox"
        name="reminder"
      />
    </div>

    <div class="mb-3">
      <CustomButton
        text="ADD TODO"
        color="red"
        type="secondary"
        submitType="submit"
      />
    </div>
  </form>
</template>

<script>
import CustomButton from "../../components/CustomButton.vue";

export default {
  name: "AddTask",
  components: {
    CustomButton,
  },
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmitForm(e) {
      e.preventDefault();
      if (!this.text) {
        alert("Please add a task");
      }

      const newTask = {
        id: Math.floor(Math.random() * 10000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.$emit("add-task", newTask);

      // clear the form
      this.text = "";
      this.day = "";
      this.reminder = "";
    },
  },
};
</script>

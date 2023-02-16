<template>
  <button
    @click="buttonClickHandler()"
    v-if="type === 'primary'"
    class="py-2 px-4 bg-black text-white font-semibold rounded-sm shadow-md hover:bg-blue-700 focus:outline-none f"
  >
    {{ text }}
  </button>

  <button
    v-if="type === 'secondary'"
    class="py-2 px-4 bg-blue-400 text-white font-semibold rounded-sm shadow-md hover:bg-blue-700 focus:outline-none"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "CustomButton",
  props: {
    text: String,
    color: String,
    type: String,
  },
  methods: {
    buttonClickHandler() {
      console.log("Clicked the button");
    },
  },
  data: function () {
    return {};
  },
};
</script>

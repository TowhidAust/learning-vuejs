<template>
  <!--  class="py-2 px-4 bg-black text-white font-semibold rounded-sm shadow-md hover:bg-blue-700 focus:outline-none" -->
  <button
    :type="submitType"
    @click="buttonClickHandler()"
    :class="[
      submitType === 'primary'
        ? 'py-2 px-4 bg-black text-white font-semibold rounded-sm shadow-md hover:bg-blue-700 focus:outline-none'
        : 'py-2 px-4 bg-blue-400 text-white font-semibold rounded-sm shadow-md hover:bg-blue-700 focus:outline-none',
    ]"
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
    submitType: String,
  },
  methods: {
    // NOTE need to pass the button click handler with $emit
    buttonClickHandler() {
      console.log("Clicked the button");
    },
  },
  data: function () {
    return {};
  },
};
</script>

<template>
  <div class="relative md:hidden">
    <slot></slot>
    <button
      @click="previous"
      class="absolute left-3 top-48 bg-white rounded-full h-8 w-8 md:hidden flex justify-center items-center"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-5 w-5 items-center"
        viewBox="0 0 20 20"
        fill="currentColor"
      >
        <path
          fill-rule="evenodd"
          d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z"
          clip-rule="evenodd"
        />
      </svg>
    </button>
    <button
      @click="next"
      class="absolute right-3 top-48 bg-white rounded-full h-8 w-8 md:hidden flex justify-center items-center"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-5 w-5 items-center"
        viewBox="0 0 20 20"
        fill="currentColor"
      >
        <path
          fill-rule="evenodd"
          d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
          clip-rule="evenodd"
        />
      </svg>
    </button>
  </div>
</template>
<script>
export default {
  emits: ["next", "previous"],
  data() {
    return {};
  },
  methods: {
    next() {
      this.$emit("next");
    },
    previous() {
      this.$emit("previous");
    }
  }
};
</script>
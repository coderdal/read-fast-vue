<template>
  <section
    class="w-full h-screen text-center mt-6 flex justify-center items-center"
    ref="container"
  >
    <h1
      class="text-center mb-4 text-4xl font-extrabold tracking-tight leading-none text-gray-900 md:text-5xl lg:text-6xl dark:text-white"
    >
      {{ activeText }}
    </h1>
    <h1
      v-if="isFinished"
      class="text-center text-red-700 mb-4 text-4xl font-extrabold tracking-tight leading-none text-gray-900 md:text-5xl lg:text-6xl dark:text-white"
    >
      Finished !
    </h1>
  </section>
</template>

<script>
export default {
  name: "appContainer",
  data() {
    return {
      activeText: "",
      lastIndex: 0,
      isFinished: false,
    };
  },
  methods: {
    removeInterval(interval) {
      clearInterval(interval);
    },
    finishReading() {
      setTimeout(() => {
        this.isFinished = true;
      }, 1000);

      setTimeout(() => {
        this.$emit("finished", true);
      }, 2000);
    },
    startReading() {
      let int = setInterval(() => {
        this.activeText = this.textData[this.lastIndex];
        this.lastIndex++;

        if (this.lastIndex > this.textData.length) {
          this.removeInterval(int);
          this.finishReading();
        }
      }, 300);
    },
    scrollToContainer() {
      const el = this.$refs.container;
      if (el) {
        el.scrollIntoView({ behavior: "smooth" });
      }
    },
  },
  mounted() {
    this.scrollToContainer();
    this.startReading();
  },
  props: {
    textData: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style></style>

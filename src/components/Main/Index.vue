<template>
  <main>
    <app-header />

    <text-area />
  </main>
</template>

<script>
import appHeader from "./Header/Index.vue";
import textArea from "./TextArea/Index.vue";

export default {
  name: "landingPage",
  components: {
    appHeader,
    textArea,
  },
};
</script>

<style scoped>
main {
  width: 100vw;
  height: 100%;
  min-height: 100vh;
  background: var(--bg-color);
  padding: 0 50px;
}
</style>

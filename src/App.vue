<template>
  <div id="app">
    <main-page />
  </div>
</template>

<script>
import mainPage from "@/components/Main/Index.vue";

export default {
  name: "App",
  components: {
    mainPage,
  },
};
</script>

<style>
#app {
  width: 100%;
  height: 100%;
}
</style>

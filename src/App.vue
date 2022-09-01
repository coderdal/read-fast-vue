<template>
  <div id="app">
    <landing-page />
  </div>
</template>

<script>
import LandingPage from "@/components/Landing/Index.vue";

export default {
  name: "App",
  components: {
    LandingPage,
  },
};
</script>

<style>
#app {
  width: 100%;
  height: 100%;
}
</style>

<template>
  <main class="w-full">
    <app-header />

    <text-area @startReading="startApp($event)" v-if="!isStarted" />

    <app-container @finished="finishApp" :textData="textData" v-else />
  </main>
</template>

<script>
import appHeader from "./Header/Index.vue";
import textArea from "./TextArea/Index.vue";
import appContainer from "./Container/Index.vue";

export default {
  name: "landingPage",
  data() {
    return {
      isStarted: false,
      textData: [],
    };
  },
  methods: {
    startApp(text) {
      this.isStarted = true;
      this.textData = text.split(" ");
    },
    finishApp() {
      this.textData = "";
      this.isStarted = false;
    },
  },
  components: {
    appHeader,
    textArea,
    appContainer,
  },
};
</script>

<style scoped>
main {
  width: 100%;
  height: 100%;
  min-height: 100vh;
  background: var(--bg-color);
  padding: 0 50px;
  overflow: hidden;
}
</style>

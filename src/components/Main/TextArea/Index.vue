<template>
  <section>
    <p
      class="text-base text-center font-medium text-gray-900 dark:text-white px-2 py-8"
    >
      To start the fast reading application, please enter the text you will read
      in the field below and click the button.
    </p>

    <form class="text-center py-4" @submit.prevent>
      <div
        class="mb-4 w-full bg-gray-50 rounded-lg border border-gray-200 dark:bg-gray-700 dark:border-gray-600"
      >
        <div
          class="flex justify-between items-center py-2 px-3 border-b dark:border-gray-600"
        >
          <div
            class="flex flex-wrap items-center divide-gray-200 sm:divide-x dark:divide-gray-600"
          >
            <h2 class="text-center">Enter your text</h2>
          </div>

          <div
            id="tooltip-fullscreen"
            role="tooltip"
            class="inline-block absolute invisible z-10 py-2 px-3 text-sm font-medium text-white bg-gray-900 rounded-lg shadow-sm opacity-0 transition-opacity duration-300 tooltip dark:bg-gray-700"
          >
            Show full screen
            <div class="tooltip-arrow" data-popper-arrow></div>
          </div>
        </div>
        <div class="py-2 px-4 bg-white rounded-b-lg dark:bg-gray-800">
          <label for="editor" class="sr-only">Publish post</label>
          <textarea
            id="editor"
            rows="8"
            class="block px-0 w-full text-sm text-gray-800 bg-white border-0 dark:bg-gray-800 focus:ring-0 dark:text-white dark:placeholder-gray-400"
            placeholder="Write an article..."
            minlength="20"
            required
            v-model="text"
          ></textarea>
        </div>
      </div>
      <button
        type="submit"
        class="inline-flex items-center px-5 py-2.5 text-sm font-medium text-center text-white bg-blue-700 rounded-lg focus:ring-4 focus:ring-blue-200 dark:focus:ring-blue-900 hover:bg-blue-800"
        @click="startReading"
      >
        Start Reading
      </button>
    </form>
  </section>
</template>

<script>
export default {
  name: "textArea",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    startReading() {
      if (this.text.length > 20) {
        console.log(this.text);
      }
    },
  },
};
</script>

<style scoped>
form {
  max-width: 80%;
  margin: 0 auto;
}

textarea {
  font-size: 1.2em;
}
</style>

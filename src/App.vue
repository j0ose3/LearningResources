<template>
  <StoredResources :resources="storedResources" />
</template>

<script>
import StoredResources from "./components/learning-resources/StoredResources.vue";

export default {
  components: {
    StoredResources
  },
  data() {
    return {
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The official vue.js documentation",
          link: "https://vuejs.org",
        },
        {
          id: "google",
          title: "Google",
          description: "Find all the resources you could possibly find",
          link: "https://google.com",
        },
      ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

* {
  box-sizing: border-box;
}

html {
  font-family: "Roboto", sans-serif;
}

body {
  margin: 0;
}
</style>

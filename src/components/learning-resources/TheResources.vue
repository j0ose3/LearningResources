<template>
  <BaseCard>
    <BaseButton
      type="button"
      @click="setSelectedTab('StoredResources')"
      :mode="storedResButtonMode"
      >Stored Resources</BaseButton
    >
    <BaseButton
      type="button"
      @click="setSelectedTab('AddResource')"
      :mode="addResButtonMode"
      >Add Resource</BaseButton
    >
  </BaseCard>
  <KeepAlive>
    <component :is="selectedTab"> </component>
  </KeepAlive>
</template>

<script>
import StoredResources from "./StoredResources.vue";
import AddResource from "./AddResource.vue";
export default {
  components: {
    StoredResources,
    AddResource,
  },
  data() {
    return {
      selectedTab: "StoredResources",
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
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      removeResource: this.removeResource
    };
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === "StoredResources" ? null : "flat";
    },
    addResButtonMode() {
      return this.selectedTab === "AddResource" ? null : "flat";
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, link) {
      const newResource = {
        id: new Date().toISOString(),
        title,
        description,
        link,
      };

      this.storedResources.unshift(newResource);
      this.selectedTab = "StoredResources";
    },
    removeResource(id) {
      const resIndex = this.storedResources.findIndex(res => res.id === id);

      this.storedResources.splice(resIndex, 1);
    }
  },
};
</script>

<style lang="scss" scoped></style>

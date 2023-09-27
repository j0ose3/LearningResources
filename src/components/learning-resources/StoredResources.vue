<template>
  <ul class="p-0 m-auto max-w-2xl">
    <LearningResource
      v-for="res in resources"
      :key="res.id"
      :id="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    />
  </ul>
</template>

<script>
import LearningResource from "./LearningResource.vue";

export default {
    components:{
        LearningResource
    },
    inject: ['resources']
    
};
</script>

<style lang="scss" scoped></style>

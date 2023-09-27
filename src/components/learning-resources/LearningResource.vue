<template>
  <li>
    <BaseCard>
      <header class="flex justify-between items-center">
        <h3 class="text-xl my-2 font-bold">{{ title }}</h3>
        <BaseButton mode="flat" @click="removeResource(id)"> Delete </BaseButton>
      </header>

      <p class="my-2 font-medium">{{ description }}</p>
      <nav>
        <a
          :href="link"
          class="text-orange-500 hover:text-yellow-500 font-semibold"
          >View Resource</a
        >
      </nav>
    </BaseCard>
  </li>
</template>

<script>
export default {
  inject:['removeResource'],
  props: {
    id: String,
    title: String,
    description: String,
    link: String,
  },
};
</script>

<style lang="scss" scoped></style>

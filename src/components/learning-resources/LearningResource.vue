<template>
  <li>
    <div>
      <header class="flex justify-between items-center">
        <h3 class="text-xl my-2 font-bold">{{ title }}</h3>
        <button class="bg-slate-400 rounded-2xl px-3 py-1 font-normal hover:bg-slate-500">Delete</button>
      </header>
    </div>
    <p class="my-2 font-medium">{{ description }}</p>
    <nav>
      <a :href="link" class="text-orange-500 hover:text-yellow-500 font-semibold">View Resource</a>
    </nav>
  </li>
</template>

<script>
export default {
  props: {
    title: String,
    description: String,
    link: String,
  },
};
</script>

<style lang="scss" scoped></style>

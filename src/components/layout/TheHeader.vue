<template>
  <header class="flex w-full h-20 bg-[#640032] justify-center items-center">
    <h1 class="text-white m-0 font-bold font text-3xl">
      {{ title }}
    </h1>
  </header>
</template>

<script>
export default {
    props: {
        title: String
    }
};
</script>

<style lang="scss" scoped></style>

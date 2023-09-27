<template>
  <teleport to="body">
    <div
      @click="$emit('close')"
      class="fixed top-0 left-0 h-full w-full bg-[#000] opacity-75 z-10"
    ></div>
    <div
      open
      class="bg-white fixed top-1/4 left-[10%] md:left-[calc(50%-20rem)] w-[80%] md:w-[40rem] z-50 rounded-xl border-none shadow-md p-0 m-0 overflow-hidden"
    >
      <header class="bg-[#3a0061] text-white w-full p-4 font-bold">
        <slot name="header">
          <h2 class="m-0">
            {{ title }}
          </h2>
        </slot>
      </header>
      <section class="p-4">
        <slot> </slot>
      </section>
      <menu class="p-4 flex justify-end m-0">
        <slot name="actions">
          <BaseButton @click="$emit('close')">Close</BaseButton>
        </slot>
      </menu>
    </div>
  </teleport>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: false,
    },
  },
  emits: ["close"],
};
</script>

<style lang="scss" scoped></style>

<template>
  <button :mode="mode" :class="checkMode(mode)">
    <slot> </slot>
  </button>
</template>

<script>
export default {
  props: {
    mode: String,
  },
  methods: {
    checkMode(mode) {
      if (mode === "flat") {
        return "bg-transparent text-[#3a0061] color-[#3a0061] border-none rounded-lg px-3 py-1 font-medium hover:bg-[#edd2ff] active:bg-slate-400 cursor-pointer";
      } else {
        return "bg-[#3a0061] text-white border-solid border-[#3a0061] rounded-lg px-3 py-1 font-medium hover:bg-[#270041] active:bg-slate-400 cursor-pointer";
      }
    },
  },
};
</script>

<style lang="scss" scoped></style>

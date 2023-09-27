<template>
  <BaseDialog v-if="inputIsInvalid" title="Invalid Input" @close="confirmError">
    <template #default>
      <p>Unfortunately, at least one input value is invalid.</p>
      <p>
        Please check all inputs and make sure you enter all the correct values.
      </p>
    </template>
    <template #actions>
      <BaseButton @click="confirmError">Okay</BaseButton>
    </template>
  </BaseDialog>
  <BaseCard>
    <form @submit.prevent="submitData">
      <div class="my-4 mx-0">
        <label for="title" class="font-bold block mb-2">Title</label>
        <input
          id="title"
          name="title"
          type="text"
          ref="titleInput"
          class="block w-full from-inherit p-1 border border-solid border-[#ccc] focus:outline-none focus:border-[#3a0061] focus:bg-[#f7ebff]"
        />
      </div>
      <div class="my-4 mx-0">
        <label for="description" class="font-bold block mb-2"
          >Description</label
        >
        <textarea
          name="description"
          id="description"
          rows="4"
          ref="descInput"
          class="block w-full from-inherit p-1 border border-solid border-[#ccc] focus:outline-none focus:border-[#3a0061] focus:bg-[#f7ebff]"
        ></textarea>
      </div>
      <div class="my-4 mx-0">
        <label for="link" class="font-bold block mb-2">Link</label>
        <input
          id="link"
          name="link"
          type="url"
          ref="linkInput"
          class="block w-full from-inherit p-1 border border-solid border-[#ccc] focus:outline-none focus:border-[#3a0061] focus:bg-[#f7ebff]"
        />
      </div>
      <div>
        <BaseButton type="submit">Add Resource</BaseButton>
      </div>
    </form>
  </BaseCard>
</template>

<script>
export default {
  inject: ["addResource"],
  data() {
    return {
      inputIsInvalid: false,
    };
  },
  methods: {
    submitData() {
      const title = this.$refs.titleInput.value;
      const description = this.$refs.descInput.value;
      const link = this.$refs.linkInput.value;

      if (
        title.trim() === "" ||
        description.trim() === "" ||
        link.trim() === ""
      ) {
        this.inputIsInvalid = true;
        return;
      }

      this.addResource(title, description, link);
    },
    confirmError() {
      this.inputIsInvalid = false;
    },
  },
};
</script>

<style lang="scss" scoped></style>

<template>
  <form @submit.prevent="askData">
    <div class="mb-3">
      <label for="exampleInputEmail1" class="form-label">Category</label>
      <input
        type="text"
        class="form-control"
        id="exampleInputEmail1"
        v-model="search"
        aria-describedby="emailHelp"
      />
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
  </form>
</template>

<script>
export default {
  data: () => ({
    search: "",
  }),

  methods: {
    askData() {
      this.$emit("action", this.search);
    },
  },
};
</script>

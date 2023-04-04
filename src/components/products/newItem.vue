<template>
  <div class="new-item-component p-4">
    <form class="form-group">
      <label for="name">Name</label>
      <input
        name="name"
        class="form-control mb-4"
        type="text"
        placeholder="Product name"
        v-model="item.name"
      />
      <label for="price">Price</label>
      <input
        class="form-control mb-5"
        type="number"
        name="price"
        placeholder="Product price"
        v-model="item.price"
      />
      <div class="row justify-content-center">
        <div class="col-lg-4">
          <button
            type="button"
            @click.prevent="cancel"
            class="btn btn-danger w-100"
          >
            Cancel
          </button>
        </div>
        <div class="col-lg-4">
          <button
            type="button"
            @click.prevent="submit"
            class="btn btn-success w-100"
          >
            Save
          </button>
        </div>
      </div>
    </form>
  </div>
</template>
<script>
import { ElMessage } from "element-plus";
export default {
  data() {
    return {
      item: {
        name: "",
        price: "",
      },
    };
  },
  methods: {
    cancel() {
      this.item = {};
      this.$emit("cancel");
    },
    submit() {
      if (!this.item.name.length) {
        ElMessage({
          showClose: true,
          message: "Please enter product name",
          type: "warning",
        });
        return;
      }
      if (!this.item.price) {
        ElMessage({
          showClose: true,
          message: "Please enter product price",
          type: "warning",
        });
        return;
      }
      this.$emit('submit', this.item);
      this.item = {};
    },
  },
};
</script>

<template>
  <div class="product-item-component">
    <div class="container">
      <div class="d-flex align-items-end">
        <h5 class="flex-fill">{{ item.name }}</h5>
        <div class="px-3 me-5 borders">
          <h5 class="mb-0">${{ item.price }}</h5>
        </div>
        <div class="actions d-flex align-items-center">
          <button @click="$emit('edit')" class="btn btn-primary me-4">
            Edit
          </button>
          <button @click="$emit('exclude')" class="btn btn-closes">X</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    item: {
      type: Object,
      default: () => {},
    },
  },
};
</script>
<style lang="scss" scoped>
.product-item-component {
  background: #d0eee8;
  border-radius: 4px;
  padding-block: 8px;
  .btn-closes {
    background: #ff0000;
    color: #fff;
    font-size: 16px;
  }
}
</style>

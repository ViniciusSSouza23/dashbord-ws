<template>
  <div class="home-view py-5">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-8">
          <div class="header d-flex pb-4">
            <h4 class="me-4 text-decoration-underline">List of products</h4>
            <button @click="newProductModal = true" class="btn btn-success">
              + New
            </button>
          </div>
          <div class="body py-5">
            <div v-if="products.length">
              <product-item
                class="mb-4"
                v-for="(product, i) in products"
                :key="i"
                :item="product"
                @edit="editItem(i)"
                @exclude="excludeItem(i)"
              />
            </div>

            <em v-else>there is no product registered yet</em>
          </div>
        </div>
      </div>
    </div>
    <el-dialog v-model="newProductModal">
      <new-item @cancel="newProductModal = false" @submit="addNew" />
    </el-dialog>
  </div>
</template>
<script>
import ProductItem from "@/components/products/ProductItem.vue";
import newItem from "@/components/products/newItem.vue";
export default {
  components: { ProductItem, newItem },
  data() {
    return {
      products: [],
      editProducts: null,
      newProductModal: false,
    };
  },
  methods: {
    addNew(item) {
      this.newProductModal = false;
      this.products.push(item);
    },
    excludeItem(i) {
      this.products.splice(i, 1);
    },
  },
};
</script>
<style lang="scss" scoped>
.home-view {
  min-height: 80vh;
  .header {
    border-bottom: 1px solid #000;
  }

  .body {
  }
}
</style>

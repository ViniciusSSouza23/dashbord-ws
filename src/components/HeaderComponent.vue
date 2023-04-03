<template>
  <div class="header-component bg-dark text-white">
    <div class="container d-flex align-items-center">
      <button
        v-if="!openSidebar"
        class="btn d-flex flex-column my-0"
        @click="openSidebar = !openSidebar"
      >
        <span class="icon">|||</span>
      </button>
      <div class="flex-fill py-4">
        <h5 class="text-center my-0">My Products admin</h5>
      </div>
    </div>
    <sidebar-component @close="openSidebar = false" v-if="openSidebar" />
  </div>
</template>
<script>
import SidebarComponent from "./SidebarComponent.vue";
export default {
  components: {
    SidebarComponent,
  },
  data() {
    return {
      openSidebar: false,
    };
  },
};
</script>
<style lang="scss" scoped>
.header-component {
  .icon {
    font-size: 20px;
    transform: rotate(90deg);
  }

  .btn {
    color: #fff;
  }
}
</style>

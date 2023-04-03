<template>
  <div class="sidebar-component bg-dark">
    <div class="container">
      <div class="d-flex justify-content-end w-100 mb-4 pt-3">
        <button @click="$emit('close')" class="btn btn-clos text-white">
          X
        </button>
      </div>
      <div class="d-flex flex-column">
        <router-link class="select" to="/">Products</router-link>
        <router-link disabled class="my-3" to="/">Company Profile</router-link>
        <router-link disabled to="/">Logout</router-link>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.sidebar-component {
  position: absolute;
  width: 20vw;
  top: 70px;
  min-height: 40vh;
  .btn-clos {
    font-size: 20px;
  }
  a {
    color: #fff;
    text-decoration: none;
    font-size: 18px;
    &:hover {
      filter: brightness(80%);
    }

    &.select {
      text-decoration: underline;
      font-size: 22px;
    }
  }
}
</style>

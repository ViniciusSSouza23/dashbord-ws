<template>
  <header-component />
  <router-view />
  <footer-component />
</template>
<script>
import FooterComponent from "@/components/FooterComponent.vue";
import HeaderComponent from "@/components/HeaderComponent.vue";
export default {
  components: { FooterComponent, HeaderComponent },
};
</script>

<style lang="scss"></style>

<template>
  <component :is="layout">
    <router-view></router-view>
  </component>
</template>
<script setup>
import MainLayout from "@/layout/MainLayout.vue";
import AuthLayout from "./layout/AuthLayout.vue";

import { useRoute } from "vue-router";
import { computed, ref } from "vue";

const route = useRoute();
const layout = computed(() => {
  return route.meta.MainLayout ? MainLayout : AuthLayout;
});
</script>
<style lang="scss">
@import "./assets/index.scss";
</style>

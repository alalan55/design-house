<script setup>
import { RouterView } from "vue-router";
import AppBar from "@/components/organisms/appBar.vue";
import AppFooter from "@/components/organisms/appFooter.vue";
</script>

<template>
  <div class="base-layout">
    <header class="base-layout__header">
      <AppBar />
    </header>
    <div class="base-layout__body">
      <RouterView />
    </div>
    <div class="base-layout__footer">
      <AppFooter />
    </div>
  </div>
</template>

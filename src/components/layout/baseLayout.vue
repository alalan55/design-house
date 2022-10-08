<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <div class="base-layout">
    <header class="base-layout__header"></header>
    <div class="base-layout__body">
      <RouterView />
    </div>
  </div>
</template>

<style lang="scss" scoped></style>

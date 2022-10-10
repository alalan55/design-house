<script setup></script>

<template>
  <div class="about-template">Página de sobre</div>
</template>

<script setup></script>

<style lang="scss" scoped>
@import "@/assets/index.scss";

.about-template {
  min-height: calc(100vh - $dh-footer-heigth);
  @include maxPageSize;

  @media (min-width: 1600px) {
    @include maxPageSizeLargeScreen;
  }
}
</style>

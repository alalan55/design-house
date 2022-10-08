<template>
  <div class="nav-container">
    <nav>barra de navegação</nav>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
@import "@/assets/index.scss";

.nav-container {
//   border: 2px solid red;
  height: $dh-nav-container-height;
  display: flex;
  align-items: center;
  justify-content: center;
  nav {
    border: 2px solid red;
    width: 95%;
    height: $dh-nav-height;
  }
}
</style>

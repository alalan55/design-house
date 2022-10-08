<template>
  <div class="nav-container">
    <nav class="navbar">
      <div class="navbar__icon">
        <span> Furniture. </span>
      </div>
      <div class="navbar__links">
        <ul>
          <li v-for="(item, idx) in links" :key="idx">
            <RouterLink :to="item.path">{{ item.name }}</RouterLink>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>

<script setup>
import { RouterLink } from "vue-router";
const links = [
  {
    name: "Home",
    path: "/",
  },
  {
    name: "Sobre",
    path: "/",
  },
  {
    name: "Galeria",
    path: "/",
  },
  {
    name: "Fale Conosco",
    path: "/",
  },
];
</script>

<style lang="scss" scoped>
@import "@/assets/index.scss";

.nav-container {
  //   width: 100%;
  height: $dh-nav-container-height;
  display: flex;
  align-items: center;
  justify-content: center;
  position: fixed;
  //   border: 2px solid blue;
  right: 0;
  left: 0;
  // top: 0;
  .navbar {
    // border: 2px solid red;
    width: 80%;
    height: $dh-nav-height;
    border-radius: 10px;
    padding: 1rem 2.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: rgba(255, 255, 255, 0.9);
    -webkit-backdrop-filter: blur(10px);
    backdrop-filter: blur(5px);
    &__icon {
      span {
        font-weight: 700;
        font-size: 1.15em;
        color: $dh-black-1;
      }
    }
    &__links {
      ul {
        padding: 0;
        display: flex;
        align-items: center;
        gap: 1rem;
        li {
          list-style: none;
          a {
            text-decoration: none;
            color: $dh-black-1;
            font-weight: 500;
          }
        }
      }
    }
  }
}
</style>

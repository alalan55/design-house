<template>
  <div class="nav-container">
    <nav class="navbar">
      <div class="navbar__icon">
        <span> Furniture. </span>
      </div>
      <div ref="navLinks" class="navbar__links">
        <ul>
          <li v-for="(item, idx) in links" :key="idx">
            <RouterLink :to="item.path">{{ item.name }}</RouterLink>
          </li>
        </ul>
      </div>
      <div class="navbar__menu">
        <img
          v-if="!showDrawer"
          @click="showDrawer = true"
          src="/icons/menu-icon.svg"
          alt="Menu"
        />
        <img
          v-else
          @click="showDrawer = false"
          src="/icons/menu-close-icon.svg"
          alt="Menu close"
        />
      </div>
    </nav>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";
import { RouterLink } from "vue-router";
import { onClickOutside } from "@vueuse/core";

const showDrawer = ref(false);
const navLinks = ref(null);
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

watch(showDrawer, (nv) => {
  nv ? (navLinks.value.style.left = "-1px") : (navLinks.value.style.left = "-100%");
});

onClickOutside(navLinks, () => {
  navLinks.value.style.left = "-100%";
  showDrawer.value = false;
});
</script>

<style lang="scss" scoped>
@import "@/assets/index.scss";

.nav-container {
  height: $dh-nav-container-height;
  display: flex;
  align-items: center;
  justify-content: center;
  position: fixed;
  right: 0;
  left: 0;
  @include transition;
  .navbar {
    position: relative;
    width: 80%;
    height: $dh-nav-height;
    border-radius: 10px;
    padding: 1rem 2.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(255, 255, 255, 0.9);
    box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.08);
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.18);
    @include transition;
    &__icon {
      span {
        font-weight: 700;
        font-size: 1.15em;
        color: $dh-black-1;
      }
    }
    &__links {
      @include transition;
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
    &__menu {
      display: none;
    }
  }
  @media (max-width: $dh-mobile) {
    align-items: flex-start;
    height: auto;
    .navbar {
      width: 100%;
      border-radius: 0px;

      &__links {
        position: absolute;
        left: -100%;
        top: -2px;
        height: 100vh;
        width: 80%;
        background: white;
        padding: 0 !important;
        margin: 0 !important;
        ul {
          height: 100%;
          margin: 0;
          display: flex;
          flex-direction: column;
          align-items: center;
          justify-content: center;

          li {
            margin: 1rem 0;
            a {
              font-weight: 600;
              font-size: 1.1em;
            }
          }
        }
      }
      &__menu {
        display: block;
        img {
          width: 30px;
          cursor: pointer;
        }
      }
    }
  }
}
</style>

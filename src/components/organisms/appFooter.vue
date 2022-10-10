<script setup>
const medias = [
  {
    name: "Facebook",
    icon: "/icons/facebook-icon.svg",
    url: "",
  },
  {
    name: "Instagram",
    icon: "/icons/instagram-icon.svg",
    url: "",
  },
  {
    name: "Linkedin",
    icon: "/icons/linkedin-icon.svg",
    url: "",
  },
  {
    name: "YouTube",
    icon: "/icons/yt-icon.svg",
    url: "",
  },
];
</script>

<template>
  <footer>
    <div class="logo">
      <span> Furniture. </span>
    </div>
    <div class="medias">
      <ul>
        <li v-for="(item, i) in medias" :key="i">
          <a :href="item.url">
            <img :src="item.icon" :alt="item.name" />
          </a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@import "@/assets/index.scss";
footer {
  padding: $dh-s-2;
  background: $dh-black-1;
  color: white;
  border-top: 1px solid white;

  display: flex;
  align-items: center;
  justify-content: space-between;
  & > div {
    flex: 1 1 auto;
  }
  .medias {
    ul {
      padding: 0;
      display: flex;
      justify-content: flex-end;
      gap: $dh-s-1;

      li {
        list-style: none;
        margin: 0;
        padding: 0 !important;
        display: flex;

        align-items: center;
        justify-content: center;
        a {
          text-decoration: none;
          padding: 0 !important;
          display: block;
          width: 30px;
          height: 30px;
          display: flex;
          align-items: center;
          justify-content: center;
          img {
            width: 100%;
            height: 100%;
            object-fit: contain;
            display: block;
          }
          transition: .2s ease-in-out;
          &:hover{
            transform: translateY(-3px);
          }
        }
      }
    }
  }
}
</style>

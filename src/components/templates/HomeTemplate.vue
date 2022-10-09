<template>
  <main class="home-template">
    <div class="home-template__cover">
      <div class="home-template__cover__texts">
        <div class="home-template__cover__texts__infos">
          <h1>Masterpieces crafted from solid wood</h1>
          <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Recusandae sunt,
            blanditiis doloremque quibusdam laborum nesciunt.
          </p>
        </div>
        <div class="home-template__cover__texts__mouse">
          <figure>
            <img src="/icons/mouse-icon.svg" alt="Scroll down" />
          </figure>
        </div>
      </div>
    </div>
    <div class="home-template__infos"></div>
  </main>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "@/assets/index.scss";
.home-template {
  //   border: 2px solid yellow;
  &__cover {
    height: 100vh;
    background: url("/img/cover.jpg") no-repeat;
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
    &__texts {
      height: 100%;
      max-height: 100%;
      display: flex;
      align-items: flex-end;
      // align-items: center;
      color: white;
      background: rgb(0, 0, 0);
      background: linear-gradient(
        0deg,
        rgba(0, 0, 0, 0.8) 0%,
        rgba(0, 0, 0, 0.15449929971988796) 71%
      );
      padding: 0 $dh-s-5;
      & > div {
        flex: 1 1 auto;
        padding: $dh-s-3 0;
      }
      &__mouse {
        display: flex;
        align-items: center;
        justify-content: flex-end;
        figure {
          width: 50px;
          img {
            width: 90%;
            height: 90%;
            object-fit: contain;
            transform: rotate(180deg);
          }
        }
      }

      @media (max-width: $dh-mobile) {
        padding: 0 $dh-s-1;
        &__infos {
          h1 {
            font-size: 1.1em;
          }
          p {
            font-size: 0.8em;
          }
        }
        &__mouse {
          figure {
            width: 30px;
          }
        }
      }
    }
  }
  &__infos {
    height: 100vh;
  }
}
</style>

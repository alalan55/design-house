<script setup></script>

<template>
  <div class="about-template">
    <div class="about-template__title">
      <h1>Sobre nós.</h1>
    </div>
    <div class="about-template__infos">
      <div class="left">
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dolorem eveniet
          laudantium rem dignissimos quasi earum, consequuntur at mollitia explicabo enim
          nisi provident doloribus neque consectetur saepe repellendus possimus esse iste!
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Non quis, consequuntur
          magni fugiat, aliquam esse deleniti consequatur tenetur a velit ipsam asperiores
          harum libero officiis inventore laboriosam! Labore, sint iusto?
        </p>
      </div>
      <div class="right">
        <figure>
          <img src="/img/about.jpg" alt="About" />
        </figure>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/assets/index.scss";

.about-template {
  @include maxPageSize;
  min-height: calc(80vh - $dh-footer-heigth);
  padding: $dh-top-containers 0 0 0;
  color: $dh-black-1;
  &__title {
    @include transition;
    @media (max-width: $dh-mobile) {
      text-align: center;
    }
  }
  &__infos {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: $dh-s-1;
    & > div {
      flex: 1 1 500px;
    }

    .right {
      display: flex;
      align-items: center;
      justify-content: center;
      figure {
        width: 500px;
        img {
          border-radius: 50px;
          width: 100%;
          height: 100%;
          object-fit: cover;
          @include transition;
        }

        @media (max-width: $dh-mobile) {
          width: 100%;

          img {
            border-radius: 30px;
          }
        }
      }
    }
    .left {
      p {
        letter-spacing: 0.3px;
        line-height: 1.45;
      }

      @media (max-width: $dh-mobile) {
        text-align: center;
      }
    }
  }

  @media (min-width: 1600px) {
    @include maxPageSizeLargeScreen;
  }
  @media (max-width: $dh-mobile) {
    padding: $dh-nav-container-height-mobile $dh-s-1 $dh-s-1;
  }
}
</style>

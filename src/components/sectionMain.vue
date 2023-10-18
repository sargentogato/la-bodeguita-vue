<template>
  <section class="row">
    <div class="imageBox col-12 col-md-4" v-for="imageText in props.imageText">
      <picture class="imageBox__picture">
        <source
          media="(min-width:768px)"
          :srcset="getImage(imageText.desktop)"
        />
        <source media="(min-width:0px)" :srcset="getImage(imageText.mobile)" />
        <img :src="getImage(imageText.desktop)" alt="" />
      </picture>
      <div class="imageBox__text-container">
        <a href="https://aluna.uk.com/" class="imageBox__link">
          <p class="imageBox__text mb-0">{{ imageText.lineOne }}</p>
          <p class="imageBox__text mb-0">{{ imageText.lineTwo }}</p>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
const props = defineProps(["imageText"])

function getImage(url) {
  return new URL(`${url}`, import.meta.url).href
}
</script>

<style lang="scss" scoped>
//fixing Bootstrap
.row > * {
  padding: 0;
}

a {
  text-decoration: none;
}

section {
  height: 100vh;
}

.imageBox {
  position: relative;
  height: 360px;
  display: flex;
  justify-content: center;
  align-items: center;

  img {
    object-fit: cover;
    height: 360px;
    filter: brightness(50%);
  }

  &__text-container {
    border: 3px solid rgb(255, 255, 255);
    position: absolute;
    padding: $pad-imageBoxes;
    text-align: center;
    z-index: 1;
  }

  &__link {
    color: white;
    letter-spacing: 0.2em;
  }

  &__text {
    font-size: $subtitle-size-mobile;
    font-family: $subtitle-fontFamily;
    font-weight: bold;
    text-shadow: $text-shadow;
  }
}

@media (width > 767px) {
  .row {
    overflow-x: hidden;

    .imageBox:last-child img {
      width: fit-content;
    }
  }

  .imageBox {
    &__text {
      font-size: $subtitle-size-tablet;
    }

    &__text-container {
      transform: translateX(-20%);
    }
  }

  .imageBox {
    height: auto;

    img {
      width: 140%;
      position: absolute;
      top: 0;
      left: -100px;
      object-fit: cover;
      height: 100vh;
      clip-path: polygon(100px 0, 100% 0, calc(100% - 100px) 100%, 0 100%);
    }
  }
}

@media (width > 1130px) {
  .row {
    .imageBox:last-child img {
      transform: translateX(10%);
    }
  }
}

@media (min-width: 1131px) and (max-width: 1299px) {
  .row {
    .imageBox:last-child img {
      transform: translateX(8.5%);
      width: fit-content;
    }
  }
}

@media (min-width: 1300px) and (max-width: 1360px) {
  .row {
    .imageBox:last-child img {
      transform: translateX(12%);
      width: fit-content;
    }
  }
}
@media (min-width: 1361px) and (max-width: 1400px) {
  .row {
    .imageBox:last-child img {
      transform: translateX(13%);
      width: 130%;
    }
  }
}

@media (width > 1400px) {
  .row {
    .imageBox:last-child img {
      width: 130%;
    }
  }

  .imageBox {
    &__text {
      font-size: $subtitle-size-desktop;
    }
  }
}

//Media queries Devices
//Landscape
@media (min-width: $iphones-min-lanscape) and (max-width: $iphone-xr) {
  .row {
    .imageBox:last-child img {
      width: 180%;
    }
  }
}
@media (width > $galaxy-s20-ultra) {
  .row {
    .imageBox:last-child img {
      width: 160%;
      transform: translateX(3.5%);
    }
  }
}
</style>

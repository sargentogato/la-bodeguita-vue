<template>
  <section class="row">
    <div
      class="imageBox col-12 col-md-4"
      :class="imageText.lineOne"
      v-for="imageText in props.imageText"
    >
      <picture class="imageBox__picture">
        <source
          media="(min-width:768px)"
          :srcset="getImage(imageText.desktop)"
        />
        <source media="(min-width:0px)" :srcset="getImage(imageText.mobile)" />
        <img :src="getImage(imageText.desktop)" alt="" />
      </picture>

      <a
        @click="addModal(imageText.lineOne)"
        class="imageBox__link"
        :class="imageText.lineOne"
      >
        <p class="imageBox__text mb-0">{{ imageText.lineOne }}</p>
        <p class="imageBox__text mb-0">{{ imageText.lineTwo }}</p>
      </a>
    </div>
  </section>
</template>

<script setup>
const props = defineProps(["imageText"])
const emit = defineEmits(["addModal"])

function getImage(image) {
  const path = new URL("../../public/images", import.meta.url).href

  return `${path}/${image}`
}

function addModal(event) {
  emit("addModal", event)
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
  align-items: center;
  display: flex;
  height: 360px;
  justify-content: center;
  position: relative;

  img {
    height: 360px;
    filter: brightness(50%);
    object-fit: cover;
  }

  &__link {
    border: 3px solid rgb(255, 255, 255);
    color: white;
    letter-spacing: 0.2em;
    position: absolute;
    padding: $pad-imageBoxes;
    text-align: center;
    z-index: 1;
  }

  &__text {
    font-size: $subtitle-size-mobile;
    font-family: $subtitle-fontFamily;
    font-weight: bold;
    text-shadow: $text-shadow;
  }
}

/** Animation when the page loads - Place all elements on the viewport */
//Catering
@keyframes catering {
  from {
    transform: translateX(-100%);
  }
}
.row .Catering {
  animation: catering $time-animation;
}

// Cooking 2
@keyframes cooking {
  from {
    transform: translateY(100%);
  }
}
.row .Cooking {
  animation: cooking $time-animation;
}

//Corsi 3
@keyframes corsi {
  from {
    transform: translateY(-100%);
  }
}
.row .Corsi {
  animation: corsi $time-animation;
}

//Media Queries
@media (width > 767px) {
  .row {
    overflow-x: hidden;

    .imageBox:last-child img {
      transform: translateX(1%);
    }
  }

  .imageBox {
    &__text {
      font-size: $subtitle-size-tablet;
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
  .imageBox:first-child img {
    clip-path: polygon(0 0, 100% 0%, 100% 100%, 0% 100%);
  }
}

@media (min-height: 400px) and (max-height: 450px) and (min-width: 768px) and (max-width: 915px) {
  .imageBox:first-child img {
    transform: translateX(15%);
    clip-path: polygon(0 0, 100% 0%, 100% 100%, 0% 100%);
  }
  .imageBox:nth-child(2) img {
    transform: translateX(15%);
  }
  .imageBox:last-child img {
    transform: translateX(10%);
    clip-path: polygon(25% 0, 100% 0%, 100% 100%, 0 100%);
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

  .imageBox {
    &__link {
      transform: translateX(-15%);
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

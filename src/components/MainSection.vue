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
a {
  text-decoration: none;
}

section {
  height: 100vh;
  // overflow: hidden;
}

.header {
  position: absolute;
  width: 100%;

  &__title {
    color: white;
    font-size: $title-size-mobile;
    font-family: $title-fontFamily;
    text-align: center;
    text-shadow: $text-shadow;
    width: fit-content;
    z-index: 1;
  }
}

@media (width > 767px) {
  .header {
    &__title {
      font-size: $title-size-lg;
    }
  }
}

@media (width > 1400px) {
  .header {
    &__title {
      font-size: $title-size-xl;
    }
  }
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

@media (width > 768px) {
  .imageBox {
    height: 100%;

    picture,
    img {
      height: 100%;
    }
  }

  .imageBox {
    &:first-child img {
      width: calc(100% + 50px);
    }

    &:nth-child(2) img {
      width: calc(100% + 200px);
      transform: translateX(-15%);
      clip-path: polygon(70px 0, 100% 0, calc(100% - 100px) 100%, 0 100%);
    }

    &:last-child img {
      width: calc(100% + 200px);
      transform: translateX(-15%);
      clip-path: polygon(75px 0, 100% 0, 100% 100%, 0 100%);
    }

    &:first-child &__link {
      transform: translateX(-10%);
    }

    &:nth-child(2) &__link {
      transform: translateX(-15%);
    }

    &:last-child &__link {
      transform: translate(-10%);
    }

    &__text {
      font-size: $subtitle-size-tablet;
    }
  }
}

@media (width > 1400px) {
  .imageBox {
    &:nth-child(2) &__link {
      transform: translateX(-50%);
    }
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
</style>

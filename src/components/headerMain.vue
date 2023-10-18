<template>
  <div class="header row d-flex justify-content-center">
    <h1 class="header__title col-12 text-center p-3">La Bodeguita del Sur</h1>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.header {
  &__title {
    position: absolute;
    color: white;
    font-size: $title-size-mobile;
    font-family: $title-fontFamily;

    text-shadow: $text-shadow;
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
</style>

<template>
  <div class="container-fluid">
    <HeaderMain />
    <SectionMain :imageText="imageText" />
  </div>
</template>

<script setup>
import HeaderMain from "./components/headerMain.vue"
import SectionMain from "./components/sectionMain.vue"

import { ref } from "vue"

const imageText = ref([
  {
    lineOne: "Catering",
    lineTwo: "spagnolo",
    mobile: "../assets/images/La-Bodeguita-del-sur-m1.jpg",
    desktop: "../assets/images/La-Bodeguita-del-sur-d1.jpg",
  },
  {
    lineOne: "Cooking",
    lineTwo: "class",
    mobile: "../assets/images/La-Bodeguita-del-sur-m2.jpg",
    desktop: "../assets/images/La-Bodeguita-del-sur-d2.jpg",
  },
  {
    lineOne: "Corsi di",
    lineTwo: "spagnolo",
    mobile: "../assets/images/La-Bodeguita-del-sur-m3.jpg",
    desktop: "../assets/images/La-Bodeguita-del-sur-d3.jpg",
  },
])
</script>

<style lang="scss" scoped></style>

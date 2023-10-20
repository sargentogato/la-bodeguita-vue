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
    mobile: "La_Bodeguita_del_sur_m1.jpg",
    desktop: "La_Bodeguita_del_sur_d1.jpg",
  },
  {
    lineOne: "Cooking",
    lineTwo: "class",
    mobile: "La_Bodeguita_del_sur_m2.jpg",
    desktop: "La_Bodeguita_del_sur_d2.jpg",
  },
  {
    lineOne: "Corsi di",
    lineTwo: "spagnolo",
    mobile: "La_Bodeguita_del_sur_m3.jpg",
    desktop: "La_Bodeguita_del_sur_d3.jpg",
  },
])
</script>

<style lang="scss" scoped></style>

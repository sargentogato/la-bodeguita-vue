<template>
  <div class="container-fluid">
    <HeaderMain />
    <SectionMain :imageText="imageText" @addModal="openModal($event)" />
    <Modal :show="showModal" @closeModal="showModal = false">
      <template #content>
        <Catering v-if="infoToShow === 'Catering'" />
        <Cooking v-if="infoToShow === 'Cooking'" />
        <Corsi v-if="infoToShow === 'Corsi di'" />
      </template>
    </Modal>
  </div>
</template>

<script setup>
import HeaderMain from "../components/MainHeader.vue"
import SectionMain from "../components/MainSection.vue"
import Modal from "../components/Modal.vue"
import Catering from "../components/Catering.vue"
import Cooking from "../components/Cooking.vue"
import Corsi from "../components/Corsi.vue"
import { imageText } from "../info/info.js"

import { ref } from "vue"

let showModal = ref(false)
let infoToShow = ref()

function openModal(event) {
  infoToShow = event
  showModal.value = true
}
</script>

<style lang="scss" scoped>
.container-fluid {
  overflow: hidden;
  padding-left: 0;
  padding-right: 0;
}
</style>

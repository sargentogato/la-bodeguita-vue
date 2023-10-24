<template>
  <div class="modal" v-if="show">
    <div class="modalBox">
      <button class="modalBox__button" @click="$emit('closeModal')">X</button>
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script setup>
defineProps({
  show: Boolean,
})
</script>

<style lang="scss" scoped>
.modal {
  position: absolute;
  inset: 0;
  background-color: rgba(107, 107, 107, 0.559);
  z-index: 2;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modalBox {
  background-color: white;
  width: fit-content;
  height: fit-content;
  max-width: 95%;
  padding: 25px;
  position: relative;
}

.modalBox__button {
  border: 1px solid rgb(141, 141, 141);
  position: absolute;
  right: -10px;
  top: -20px;
  width: $button-square;
  height: $button-square;
  border-radius: 50%;
  background-color: rgb(47, 145, 18);
  color: white;
  font-weight: bold;
  font-size: 1.8rem;

  &--close {
    display: none;
  }
}
</style>

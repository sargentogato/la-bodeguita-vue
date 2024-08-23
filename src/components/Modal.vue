<template>
  <Transition name="modal">
    <div class="modal" v-if="show">
      <div class="modalBox">
        <slot name="content"></slot>
        <button class="modalBox__button" @click="closeModal">X</button>
      </div>
    </div>
  </Transition>
</template>

<script setup>
defineProps({
  show: Boolean,
});

const emit = defineEmits(["close"]);

function closeModal() {
  emit("close");
}
</script>

<style lang="scss" scoped>
.modal {
  position: fixed;
  background-color: rgba(107, 107, 107, 0.559);
  z-index: 2;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.modalBox {
  background-color: rgb(0, 0, 0);
  max-width: 90%;
  padding: 25px;
  position: relative;
  top: 50px;
  height: 100%;
  overflow-y: scroll;
}

.modalBox__button {
  border: 1px solid rgb(141, 141, 141);
  position: absolute;
  right: 1px;
  top: 1px;
  width: $button-square;
  height: $button-square;
  border-radius: 50%;
  background-color: rgb(47, 145, 18);
  color: white;
  font-weight: bold;
  font-size: 1.5rem;

  &--close {
    display: none;
  }
}

.modal-enter-active {
  transition: opacity 800ms ease;
}
.modal-leave-active {
  transition: opacity 200ms ease;
}

.modal-enter-from,
.modal-leave-to {
  opacity: 0;
}

@media (min-width: 520px) {
  .modalBox {
    height: fit-content;
    top: 0;
    max-width: 600px;
  }
}
</style>

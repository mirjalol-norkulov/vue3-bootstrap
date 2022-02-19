<script>
import BButton from "./components/BButton.vue";
import BButtonGroup from "./components/BButtonGroup.vue";
import BModal from "./components/BModal.vue";

export default {
  components: { BButton, BButtonGroup, BModal },
  data() {
    return {
      showModal: true,
    };
  },
};
</script>

<template>
  <div class="app">
    <BButtonGroup size="sm">
      <BButton :variant="'danger'"> Button 1</BButton>
      <BButton :variant="'danger'" outlined> Button 2</BButton>
      <BButton :variant="'danger'"> Button 3</BButton>
    </BButtonGroup>
    <BModal :open="showModal">
      <template v-slot:title> Modal title </template>
      This is modal body

      <template v-slot:footer>
        <BButton type="button" @click="showModal = false">Close</BButton>
        <BButton type="button">Save changes</BButton>
      </template>
    </BModal>
  </div>
</template>

<style>
.app {
  padding: 2rem;
}
</style>

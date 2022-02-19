<script>
import { Modal } from "bootstrap";

export default {
  name: "BModal",
  props: {
    open: {
      type: Boolean,
      default: false,
    },
  },
  mounted() {
    this.modal = new Modal(this.$el);
    if (this.open) {
      this.modal.show();
    }
  },
  watch: {
    open: {
      immediate: true,
      handler() {
        if (!this.modal) {
          return;
        }

        if (this.open) {
          this.modal.show();
        } else {
          this.modal.hide();
        }
      },
    },
  },
};
</script>

<template>
  <div class="modal" tabindex="-1">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">
            <!-- Named slot -->
            <slot name="title" />
          </h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <slot />
        </div>
        <div class="modal-footer">
          <slot name="footer" />
        </div>
      </div>
    </div>
  </div>
</template>

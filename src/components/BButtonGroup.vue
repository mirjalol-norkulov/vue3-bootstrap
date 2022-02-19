<script>
export default {
  props: {
    size: {
      type: String,
      default: undefined,
      validator(value) {
        return ["sm", "lg"].includes(value);
      },
    },
    vertical: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<template>
  <div
    class="btn-group"
    :class="[
      size ? `btn-group-${size}` : '',
      vertical ? 'btn-group-vertical' : '',
    ]"
  >
    <slot />
  </div>
</template>

<style></style>

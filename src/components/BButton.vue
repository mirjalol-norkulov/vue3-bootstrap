<script>
export default {
  name: "BButton",
  props: {
    variant: {
      type: String,
      default: "primary",
      validator(value) {
        return [
          "primary",
          "secondary",
          "success",
          "danger",
          "warning",
          "info",
          "light",
          "dark",
          "link",
        ].includes(value);
      },
    },
    outlined: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: undefined,
      validator(value) {
        return ["sm", "lg"].includes(value);
      },
    },
  },
};
</script>

<template>
  <button
    class="btn"
    :class="[
      'btn-' + (outlined ? 'outline-' : '') + variant,
      size ? `btn-${size}` : '',
    ]"
  >
    <!-- Default slot -->
    <slot />
  </button>
</template>

<style></style>

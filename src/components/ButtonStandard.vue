<template>
  <button>
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "ButtonStandard",
  props: {
    type: {
      type: String,
      default: "button",
    },
  },
};
</script>

<style lang="scss" scoped></style>

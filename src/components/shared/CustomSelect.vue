<template>
  <select
    v-bind="$attrs"
    class="custom-select"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  >
    <option v-for="item in formatedItems" :value="item.value" :key="item.value">
      {{ item.label }}
    </option>
  </select>
</template>

<script>
export default {
  name: "CustomSelect",

  props: {
    items: {
      type: Array,
      requaired: true,
    },
    modelValue: {
      type: [String, Number],
      default: "",
    },
  },

  computed: {
    formatedItems() {
      return this.items.map((item) => {
        return typeof item === "object" ? item : { value: item, label: item };
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
.custom-select {
  height: 40px;
  max-width: 220px;
  width: 100%;
  border: 2px solid $main-color;
  font-size: 18px;
  outline: none;
  padding: 8px 15px;
  cursor: pointer;
  display: inline-block;
}
</style>

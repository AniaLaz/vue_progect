<template>
  <Container>
    <slot name="title"></slot>
    <div class="apartment-list">
      <template v-for="apartment in items">
        <slot name="apartment" v-bind:apartment="apartment"></slot>
      </template>
    </div>
  </Container>
</template>

<script>
import Container from "../shared/BoxContainer.vue";

export default {
  name: "ApartmentsList",
  components: {
    Container,
  },
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style lang="scss" scoped>
.apartment-list {
  display: flex;
  flex-wrap: wrap;
  margin-left: -15px;
  margin-right: -15px;
}
</style>

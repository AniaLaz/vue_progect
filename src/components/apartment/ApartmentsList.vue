<template>
  <div class="apartment-list">
    <ApartmentItem
      v-for="{ id, descr, price, rating, imgUrl } in items"
      :key="id"
      :descr="descr"
      :price="price"
      :rating="rating"
      :imgSrc="imgUrl"
      class="apartment-list__item"
    />
  </div>
</template>

<script>
import ApartmentItem from "./ApartmentItem.vue";

export default {
  name: "ApartmentsList",
  components: {
    ApartmentItem,
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
  &__item {
    margin-bottom: 30px;
  }
}
</style>

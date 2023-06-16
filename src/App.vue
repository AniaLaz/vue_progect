<template>
  <h1>{{ title }}</h1>

  <ButtonStandard @click="incremen">Click me</ButtonStandard>
  <!-- <StarRating :rating="2.5" /> -->
  <h2>{{ event.text }}</h2>
  <!-- <input type="text" v-model="text" /> -->
<CustomInput type="text" label="Title" v-model="event.text" />
  <!-- <CustomInput type="text" v-model="event.title" label="Description" /> --> -->
  <ApartmentsList :items="apartments">
    <template v-slot:title>New Title </template>
    <template v-slot:apartment="{ apartment }">
      <ApartmentItem
        :key="apartment.id"
        :descr="apartment.descr"
        :price="apartment.price"
        :rating="apartment.rating"
        :imgSrc="apartment.imgUrl"
        @click="handalItemClick"
      />
    </template>
  </ApartmentsList>
</template>

<script>
import ButtonStandard from "./components/ButtonStandard.vue";
import ApartmentsList from "./components/apartment/ApartmentsList.vue";
import apartments from "./components/apartment/apartments";
import ApartmentItem from "./components/apartment/ApartmentItem.vue";
import CustomInput from "./components/shared/CustomInput.vue";

export default {
  name: "App",
  components: {
    ButtonStandard,
    ApartmentsList,
    ApartmentItem,
    CustomInput,
  },
  data() {
    return {
      event: {
             text: "",
      },
 
      amountOfClicks: 0,
      apartments,
    }
  },
  computed: {
    title() {
      return `Amount ot clicks ${this.amountOfClicks}`;
    },
  },
  methods: {
    incremen() {
      this.amountOfClicks += 1;
    },
    handalItemClick() {
      console.log("item click");
    },
  },
};
</script>

<style>
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<!-- npm run serve -->

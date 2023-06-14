<template>
  <h1>{{ title }}</h1>
  <ButtonStandard @click="incremen">Click me</ButtonStandard>
  <!-- <StarRating :rating="2.5" /> -->
    <DirectiveesTest />
    <ApartmentsList :items="apartments"/>
</template>

<script>
import ButtonStandard from "./components/ButtonStandard.vue";
import DirectiveesTest from "./components/DirectiveesTest.vue";
// import StarRating from "./components/StarRating.vue";
import ApartmentsList from "./components/apartment/ApartmentsList.vue";
import apartments from "./components/apartment/apartments";

export default {
  name: "App",
  components: {
    ButtonStandard,
    DirectiveesTest,
    // StarRating,
    ApartmentsList,
    
  },
  data() {
    return {
      amountOfClicks: 0,
      apartments,
      apartment: {
        id: "42342",
        title:
          "Aut qui adipisgi distinctio maiores molestiae sit est inventjre vero",
        descr:
          "Non perferendis rerum a in nisi exercitationem dolorum perferendis",
        price: 2032,
        rating: 4.7,
        location: {
          city: "Kherson",
        },
        owner: {
          name: "Ellen",
          phone: "1324345",
          email: "Ellen@gmail.com",
        },
      },
    };
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

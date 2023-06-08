<template>
<h1>{{title}}</h1>
  <ButtonStandard @click="incremen">Click me</ButtonStandard>

</template>

<script>

import ButtonStandard from "./components/ButtonStandard.vue";

export default {
  name: "App",
  components: {
    ButtonStandard,

  },
  data(){
    return{
        amountOfClicks: 0
    }
    },
    computed :{
      title(){
        return `Amount ot clicks ${this.amountOfClicks}`
      }
},
methods:{
  incremen(){
    this.amountOfClicks += 1
  }
}}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<!-- npm run serve -->

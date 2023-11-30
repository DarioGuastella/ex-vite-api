<script>
import axios from 'axios';
import { store } from "./store.js"
import BeerCard from "./components/BeerCard.vue"
export default {
  components: {
    BeerCard
  },
  data() {
    return {
      store,
    }
  },
  mounted() {
    this.getBeers();
    console.log(this.store)
  },
  methods: {
    getBeers() {
      axios.get(this.store.apiUrl).then(result => {
        this.store.beers = result.data;
      });
    }
  }
}
</script>

<template>
  <BeerCard v-for="beer in store.beers" :beer="beer" />
</template>

<style scoped></style>

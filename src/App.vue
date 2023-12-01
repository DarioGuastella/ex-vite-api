<script>
import axios from 'axios';
import { store } from "./store.js"
import BeerCard from "./components/BeerCard.vue"
import BeerTypeSearch from "./components/BeerTypeSearch.vue"

export default {
  components: {
    BeerCard,
    BeerTypeSearch
  },
  data() {
    return {
      store,
    }
  },
  mounted() {
    this.getBeers()
  },
  methods: {
    getBeers() {
      let apiAddress = this.store.apiUrl;
      if (this.store.beersType.length) {
        apiAddress += "&by_type=" + this.store.beersType;
        console.log(apiAddress)
      }
      axios.get(apiAddress).then(result => {
        this.store.beers = result.data;
      });

    }
  }
}
</script>

<template>
  <main>
    <h1>Le nostre birre Irlandesi</h1>
    <BeerTypeSearch @search="getBeers" />
    <div class="wrapper">
      <BeerCard v-for="beer in store.beers" :beer="beer" />
    </div>
  </main>
</template>

<style scoped>
.wrapper {
  display: flex;
  flex-wrap: wrap;
}

h1 {
  text-align: center;
  padding: 2rem;
}
</style>

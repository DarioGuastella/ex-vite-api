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
    this.getBeers()
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
  <main>
    <h1>Le nostre birre Irlandesi</h1>
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

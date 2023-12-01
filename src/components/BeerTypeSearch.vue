<script>
import { store } from "../store.js"

export default {
    name: "BeerTypeSearch",
    data() {
        return {
            store
        }
    },
    methods: {
        search() {
            console.log("Tipo di birra: ", this.store.beersType);
            this.$emit("search");
            console.log(this.store.beersType);
        }
    },
    mounted() {
    }
}
</script>

<template>
    <div>
        <label for="beers">Scegli una tipologia di birra:</label>

        <select v-model="store.beersType" name="beers" id="beers">
            <option value="">Tutte le tipologie</option>
            <option value="micro">Micro</option>
            <option value="nano">Nano</option>
            <option value="regional">Regional</option>
            <option value="brewpub">Brewpub</option>
            <option value="large">Large</option>
            <option value="planning">Planning</option>
            <option value="bar">Bar</option>
            <option value="contract">Contract</option>
            <option value="proprietor">Proprietor</option>
            <option value="closed">Closed</option>
        </select>
        <button @click="search">Cerca</button> <!-- Rigo 14 -->
    </div>
</template>

<style scoped></style>
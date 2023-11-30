<script>
export default {
    name: "BeerCard",
    props: {
        beer: Object
    }
}
</script>

<template>
    <div class="cardContainer">
        <div class="shadowBox">
            <h2>Nome birra: <br>{{ beer.name }}</h2>
            <h4>Città di provenienza: <br>{{ beer.city }}</h4>
            <h4>Indirizzo del produttore: <br>{{ beer.street }}</h4>
            <h4>Sito del produttore: <br><a href="#">{{ beer.website_url }}</a></h4>
        </div>
    </div>
</template>

<style scoped>
.cardContainer {
    width: calc(100% / 5 - 4rem);
    background-color: crimson;
    aspect-ratio: 1;
    margin: 2rem;
    line-height: 1.5;
    padding: 2rem;
    background-image: url("https://img.freepik.com/free-photo/tasty-american-beer-composition_23-2148907577.jpg?size=626&ext=jpg&ga=GA1.1.1413502914.1697068800&semt=ais");
    border-radius: 10px;
    word-break: break-all;
}



.shadowBox {
    background-color: rgba(0, 0, 0, 0.5);
    border-radius: 25px;
    padding: 2rem;
    height: 548px;
}

h4,
h2 {
    margin-bottom: 2rem;
}
</style>
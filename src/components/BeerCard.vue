<script>
export default {
    name: "BeerCard",
    props: {
        beer: Object
    }
}
</script>

<template>
    <div class="cardContainer"
        :class="beer.brewery_type == 'micro' ? 'micro' : '', beer.brewery_type == 'regional' ? 'regional' : '', beer.brewery_type == 'brewpub' ? 'brewpub' : '', beer.brewery_type == 'large' ? 'large' : ''">
        <div class="shadowBox">
            <h2>{{ beer.name }}</h2>
            <h4>Città di provenienza: <br>{{ beer.city }}</h4>
            <h4>Indirizzo del produttore: <br>{{ beer.street }}</h4>
            <h4>Sito del produttore: <br><a href="#">{{ beer.website_url }}</a></h4>
            <h4>Tipo di birra: <br>{{ beer.brewery_type }}</h4>
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
    border-radius: 10px;
    word-break: break-word;
}

.micro {
    background-image: url("https://img.freepik.com/free-photo/tasty-american-beer-composition_23-2148907577.jpg?size=626&ext=jpg&ga=GA1.1.1413502914.1697068800&semt=ais");
}

.regional {
    background-image: url("https://img.freepik.com/free-photo/delicious-american-beer-arrangement_23-2148907557.jpg?w=1380&t=st=1701447972~exp=1701448572~hmac=b2be67072c24bfb8440e08e147b13bcba2ee5de8c927e173f97f433b2aa79d37");
}

.brewpub {
    background-image: url("https://img.freepik.com/free-photo/bottle-beer-with-brewing-ingredients-hop-flower-with-wheat-top-view_639032-1944.jpg?w=1380&t=st=1701448038~exp=1701448638~hmac=fffcc00dd5c4a66f4fe01f8c9f5b9f471e856de7a88a3b2d0278dcc36219b2e8");
}

.large {
    background-image: url("https://img.freepik.com/free-photo/close-up-beer-with-snacks-wooden-table_23-2148306012.jpg?w=1380&t=st=1701448051~exp=1701448651~hmac=788a65fb1cf2b15fad5cce5e5ff0a5e2c4c2e1eca6c26c1cf5e201141681c985");
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
}</style>
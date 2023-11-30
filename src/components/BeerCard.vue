<script>
export default {
    name: "BeerCard",
    props: {
        beer: Object
    }
}
</script>

<template>
    <div>
        <div>
            <h2>{{ beer.name }}</h2>
            <h4>{{ beer.country }}</h4>
            <h4>{{ beer.city }}</h4>

        </div>
    </div>
</template>

<style scoped></style>
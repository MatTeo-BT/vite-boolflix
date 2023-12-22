<template lang="">
    <div>
        <article v-for="movie in movies">
            {{movie.title}}
            <p>Titolo originale: {{movie.original_title}}</p>
            <p>Lingua originale: {{movie.original_language}}</p>
            <p>Voto: {{movie.vote_average}}</p>
        </article>
        <article v-for='tvSeries in tvSeries'>
            <p>Titolo: {{tvSeries.name}}</p>
            <p>Titolo originale: {{tvSeries.original_name}}</p>
            <p>Lingua originale: {{tvSeries.original_language}}</p>
            <p>Voto: {{tvSeries.vote_average}}</p>
        </article>
    </div>
</template>
<script>
export default {
    name: `AppMain`,
    props: {
        movies: {
            type: Array,
            required: true
        },
        tvSeries: {
            type: Array,
            required: true
        }
    }
}
</script>
<style lang=""> 
</style>
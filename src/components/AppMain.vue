<template lang="">
    <div>
        <article v-for="movie in movies">
            {{movie.title}}
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
        }
    }
}
</script>
<style lang=""> 
</style>
<template lang="">
    <div>
        <AppSearch @serach="getMovies"/>
        <AppMain :movies="moviesList"/>
    </div>
</template>
<script>
import AppSearchVue from './components/Appsearch.vue';
import AppMain from './components/AppMain.vue';
import axios from `axios`;

export default {
    components: {
        AppSearchVue,
        AppMain
    },
    data() {
        return {
            moviesList: [],
        }
    },
    methods: {
        getMovies(searchMovie = ``) {
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=dadc09536eef8ff2ae053c9ebd6144cb&query=', searchMovie)
                .then((response) => {
                    // handle success
                    console.log(response);
                    this.moviesList = response.data.results;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });

        }
    },
    // created() {
    //     this.getMovies();
    // }
}
</script>
<style lang=""> 
</style>